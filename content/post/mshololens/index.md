---
title: Text Selection in MicroSoft HoloLens
subtitle: Given the development with AR&VR, we need a smart way to achieve the text selection in the MS Hololens. Therefore, we developed the new interation named head-tail to achieve the text selection in the MS Hololens Edge browser.

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
- Interaction Design
---

## Overview

1. I designed a state machines to record the states of the text selection.
2. I made a P2P WebRTC between the iphone Safaria and MS Hololens Edge.

## Technical Parts


### The tiny device interaction

First we have to let the iphone access the files stored from the computer. This is easily achieved by the setting up a file server by `python -m http.server -port`, and we access the computer's ip address + port to access the files.


### P2P Real Time Communication

Think we have an iphone and the MicroSoft HoloLens, how to use the button on the iphone to select the text in the Hololens? There is no extra dependency on the Toolcase of hololens, I just used the websocket communication. So the basic architecture is here:

{{< figure src="https://bravopan.github.io/hololens.png" title="" >}}

The core of the communication is `Socketio.P2P` which is in the Socketio which allows a communication between the peer and peer without server, the configuration is openning the port of the hololens, and create a socketio thread by filling in this port. The code on the iphone is bascially sending the signal when triggers the dom operation `touchstart`, `touchmove`, and `touchend`. The code in the socketio is like:

```
document.getElementbyId('pd').addEventListener('eventname', function(){
  socket.emit('An event Sginal')
  })
```

And on the Hololens edge browser, what it needs to do is just to receive the signal and render the text. The code corrosponds is:

```
socketio.on('An event Signal', function(){
    //do something
  })
```

Besides, the text has 5 states as a selection cycle:
- step 1, initialzaiton. This is to ensure the devices are all online or reset.
- step 2, head is selected and if confirmed then turns to the blue.
- step 3, tail is selected and if confirmed then turns to the blue.
- step 4, head and tail are connected.
- step 5, change the state to the step 1.

So this basically how it works. Please check on [this video](https://www.youtube.com/watch?v=fm-GnUHAk5s&t=1s) for the detail!
