---
layout: post
title:  "Using a Picture as Webcam Input"
categories: tech
permalink: picture-as-webcam-input
---

I was ordering glasses online for the first time recently. A measurement of your pupillary distance (distance between your pupils) is required. It can be measured by your optomitrist and and put down on your prescription, but you need to ask, and unfortunately I hadn't. The website claimed it was no big deal, as you could just send a picture with any plastic card against your lips, and they measure it for you. How accurate this might be, only god knows, but they seem to have a lot of faith in it. I had taken the picture on my phone through my camera app, but when uploading on my laptop, it did not give me the option to upload a picture, only to take one using my webcam. A bit ridiculous, but I knew I could get by it somehow. A bit of googling, and I figured out how to make a virtual webcam that outputs a single image.

Firstly, I had to install the v4l2loopback kernel module, and load it:

```bash
➜ xbps-install -S v4l2loopback
➜ modprobe v4l2loopback
```

Then, we can create a dummy virtual webcam with the module, using ffmpeg:

```bash
➜ ffmpeg -loop 1 -re -i /path/to/your/image.jpg -vf format=yuv420p -f v4l2 /dev/video2
```

After running this command, the dummy webcam shows up in firefox, and I'm able to take a "webcam" picture.
