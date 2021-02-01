---
title: Raspbian OS Repo Purge, Citrix
subtitle: A Company Customized Package Repository designed based on Raspbian.

# Summary for listings and search engines
summary: The proposal is to maintain a customized repo by Citrix which contains all Raspbian binary packages and has the capabilities to sync with Raspbian regularly and store our own Debian binary packages. The meaning of our project is to make it easier for WSH(Worksapce Hub) users to install the packages only by receiving several commandas. And we would optimize this project by adding a Cache Server.

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

1. We (me and 2 other teammates) finished the funcitons of synchronizing packages from the Raspbian.org with the total 77GB packages on the `Citrix Azure Repo Server`, and we coded the autoscript to update the packages on time.
2. We tested the customize company packages `WSH-CEF` (workspace hub Chromium Embedded Framework) on the client device (Raspberry Pi) by 'apt install' command.
3. We made a Cache Server by `AptCacherNg` on the Alibaba Cloud server, the statistics would appear on the browser side.

## Technical Parts

### Citrix Azure Repo server

This repo server was built based only for Debian `buster` distribution, and we have to add `Citrix` component in the pool directory to make the `apt command` recognizable. Here are two critical challenges:

- **How to colone only `buster` distribution**?

We finished this part by the command `rsync` command, the benefit is at that it does not clone the file which the modified time equals to source file, which means it would never download for the same file twice. We made the server work for both `dist` and `pool`, this also ensures the Update funciton for the later usage.

- **How to make the `apt install` command work for the client machine?**

Before we really achieved the installment function for the company pacakge, we first had to configure the repo server, we created a `citrix` distribution directory in the `dist`, and there are two files we have to notice `Release` and `InRealease`, the only difference between these two files is that `Release` needs `Release.gpg` file to be equivalent with `InRealease` for the usage of signature, the point of keeping these two kind of files is to avoid the race condition. The way we generate the `Release` and `InRealease` files are by `gpg` command. Besides, we also need the `workspacehub-cef` debian packages in the `pool` to be indexabled for the `dist/citrix/binary-armfh` (`workspacehub-cef` is a binary file), here another necessacity is to generate `Packages` file to index the `pool/citrix/workspacehub-cef`, we made it by `apt-ftparchive packages` command. The final step is on the client machine, we have to modify the `source.list` to add the ip address, distribution, and components. Finally, we could make it work on the client machine.

- **Create Accont** - HTTP GET&POST, Form Authentication, Error Message Render, Form Filter
- **Video Listing** - ORM Query, Data Plugin, URL Design, Template Rendering
- **Pagination** - URL Design, Django Pagination Robot, ORM Query, Jinja Tag Condition, Template Rendering
- **Video Sort** - URL Redirection, ORM Query by Condition&Sorting,
- **User Authentication** - Django Authentication, Session Validation, JinJa Tag Condition
- **Detial Page** - URL Config, Web Crawler, Semantic Card Component, Redirect to Home
- **Deployment** - AWS Elastic Beanstalk, Python awsebcli, Virtual Environment Configuration

## License

Copyright 2020-present [Dengpan Yuan](https://www.dengpan-yuan.xyz/).
