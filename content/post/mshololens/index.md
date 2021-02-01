---
title: Text Selection in MicroSoft HoloLens
subtitle: Given the development with AR&VR, we need a smart way to achieve the text selection in the MS Hololens. Therefore, we developed the new interation named one thumb to achieve the text selection in the MS Hololens Edge browser.

# Summary for listings and search engines
summary: This project is based on a P2P websocket that could connect MS Hololens and any smart phone (with major popular browser) to implement the text selection function in Hololens and many other headset devices. The basic idea is taking fully advantage of current devices, like smart phone everyone has as a controller to pinpoint the text position in the Hololens. The controller on the smart device is like this

# Link this post with a project
projects: []

# Date published
date: "2019-12-01T00:00:00Z"

# Date updated
lastmod: "2020-01-31T00:00:00Z"

# Is this an unpublished draft?
draft: false

# Show this page in the Featured widget?
featured: false

# Featured image
# Place an image named `featured.jpg/png` in this page's folder and customize its options here.




image:
  caption: 'Image credit: [**Text Selection in Holones Demo**](https://www.youtube.com/watch?v=fm-GnUHAk5s)'
  focal_point: ""
  placement: 2
  preview_only: false

authors:
- admin

tags:
- NetWork Application
- Research Project

categories:
- Web Application
- WebSocket Programming
---

## Overview

1. I achieved the interaction between the pressure button and path generation.
2. I implemented the core algorithm part of Dynamic Time Wrapping to suggest the words based on the simulated path list and real path list.
3. Due to the data analysis, we have to send the data from the iphone to the computer, I achieved this by WebSocket in the Javascript.

## Technical Parts

### The tiny device interaction

First we have to let the iphone access the files stored from the computer. This is easily achieved by the setting up a file server by `python -m http.server -port`, and we access the computer's ip address + port to access the files.


### The Dynamic Time Wrapping Algorithm

Here I have two arrays. We simulated the paths of the alphabetical words in the json file, and have another real sampling paths, we used the DTW algorithm which could get the minimum cost of the paths, and thus we can get the most similar one.

### Send the data back to the computer

Here I used the Websocket in the javascript, we have to create a host with the new port waiting for the data receiving in this port. And when we finished the test work, just use the websocket to send back the data of what we need to this new port.
