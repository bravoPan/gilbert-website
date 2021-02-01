---
title: Swipe-Force Keyboard in Mini-Text
subtitle: Think about if we have a tiny device (even smaller than apple watch), how could we achieve the funcion of typing the keyboard?

# Summary for listings and search engines
summary: In this project, we have proposaled a physical tiny button could be used for selecting the words by the swipe path. And I was assigned to make a virtual button to explore the potential of this interaction.

# Link this post with a project
projects: []

# Date published
date: "2019-09-01T00:00:00Z"

# Date updated
lastmod: "2019-11-31T00:00:00Z"

# Is this an unpublished draft?
draft: false

# Show this page in the Featured widget?
featured: false

# Featured image
# Place an image named `featured.jpg/png` in this page's folder and customize its options here.




image:
  caption: 'Image credit: [**Mini-Text Demo**](https://www.youtube.com/watch?v=AyK55WvJ7XU)'
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

Please check the [demo video](https://www.youtube.com/watch?v=AyK55WvJ7XU) to see how it works!

## License

Copyright 2019-present [Dengpan Yuan](https://www.dengpan-yuan.xyz/).
