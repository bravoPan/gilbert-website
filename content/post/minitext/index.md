---
title: Swipe-Force Keyboard in MiniText
subtitle: Think about if we have a tiny device (even smaller than apple watch), how could we achieve the funcion of typing the keyboard?

# Summary for listings and search engines
summary: This project is to implement the Swype keyboard on the usage of the tiny device. DTW (Dynamic Time Wrapping) algorithm will be introduced to minimize the cost for suggesting the optimal path, and also Data Retrieve and Words Suggestion will also be mentioned.

# Link this post with a project
projects: []

# Date published
date: "2019-07-01T00:00:00Z"

# Date updated
lastmod: "2019-08-31T00:00:00Z"

# Is this an unpublished draft?
draft: false

# Show this page in the Featured widget?
featured: false

# Featured image
# Place an image named `featured.jpg/png` in this page's folder and customize its options here.




image:
  caption: 'Image credit: [**Citrix Repo Demo**](https://www.youtube.com/watch?v=slrZdMhYvOg)'
  focal_point: ""
  placement: 2
  preview_only: false

authors:
- admin

tags:
- Debian Package
- Raspbian

categories:
- Cloud Application Development
- Raspbian Packages
---

## Overview

1. We (me and 2 other teammates) finished the funcitons of synchronizing packages from the Raspbian.org with the total 77GB packages on the `Repo Server` (Azure Cloud Server), and we coded the autoscript to update the packages on time.
2. We tested the customize company packages `workspacehub-cef` (workspace hub Chromium Embedded Framework) on the client device (Raspberry Pi) by `apt install` command.
3. We made a Cache Server by `AptCacherNg` on the Alibaba Cloud server, the statistics would appear on the browser side.

## Technical Parts

### Citrix `Repo Server`

This repo server was built based only for Debian `buster` distribution, and we have to add `Citrix` component in the pool directory to make the `apt command` recognizable. Here are two critical challenges:

- **How to colone only `buster` distribution**?

We finished this part by the command `rsync` command, the benefit is at that it does not clone the file which the modified time equals to source file, which means it would never download for the same file twice. We made the server work for both `dist` and `pool`, this also ensures the Update funciton for the later usage.

- **How to make the `apt install` command work for the client machine?**

Before we really achieved the installment function for the company pacakge, we first had to configure the repo server, we created a `citrix` distribution directory in the `dist`, and there are two files we have to notice `Release` and `InRealease`, the only difference between these two files is that `Release` needs `Release.gpg` file to be equivalent with `InRealease` for the usage of signature, the point of keeping these two kind of files is to avoid the race condition. The way we generate the `Release` and `InRealease` files are by `gpg` command. Besides, we also need the `workspacehub-cef` debian packages in the `pool` to be indexabled for the `dist/citrix/binary-armfh` (`workspacehub-cef` is a binary file), here another necessacity is to generate `Packages` file to index the `pool/citrix/workspacehub-cef`, we made it by `apt-ftparchive packages` command. The final step is on the client machine,

### Make it runnable on the user machine

Since we have the preparation above, the next step is just to make some modification on the user machine to connect with the repo server. We made it by modifying the `source.list` to add the ip address, distribution, and components. Finally, we could make it work on the client machine, the client machine was able to install the `workspacehub-cef` package successfully.

### Make the Cache Server to Reduce the Traffic

The last part of project is to design a `cache server` to redirect the traffic from the client machine. I personally was responsible for this critical part, I made it possible by deploying another `cache server` (Alibaba Cloud Server). The basic work here is to configure the cache machine, this contain configure the fields like `CacheDir, LogDir, Port, Remap` and etc. Eventually we have to create a configuration file named `apt-cacher-ng` on the client machine to add the acquired ip address of the `cache server`, and the command trafic will automatically be transferred to the cache server before reaching the `repo server`! For the client machine, the statistics could be viewed on the browser by the binded port.

Please check the [demo video](https://www.youtube.com/watch?v=slrZdMhYvOg) to see how it works!

## License

Copyright 2019-present [Dengpan Yuan](https://www.dengpan-yuan.xyz/).
