---
layout: post
title: Fix upside down Skype video in Ubuntu 12.10 [UPDATED]
date: '2012-11-02T23:22:00.002+01:00'
author: Morten
tags:
- Linux
- Hardware
- Ubuntu
- fix
modified_time: '2013-04-19T12:03:38.215+02:00'
blogger_id: tag:blogger.com,1999:blog-6967032375013519080.post-904542916257504825
blogger_orig_url: https://m635j520.blogspot.com/2012/11/fix-upside-down-skype-video-in-ubuntu.html
cover-img: http://farm9.staticflickr.com/8189/8119893255_ea885ba176.jpg
thumbnail-img: http://farm9.staticflickr.com/8189/8119893255_ea885ba176.jpg
share-img: http://farm9.staticflickr.com/8189/8119893255_ea885ba176.jpg
---

[![Holland](http://farm9.staticflickr.com/8189/8119893255_ea885ba176.jpg)](http://www.flickr.com/photos/mortenjohs/8119893255/ "Holland by mortenjohs, on Flickr")When launching Skype in 64-bit Ubuntu 12.10 on my Asus U35J the webcam image was all topsy-turvy. Since I don't live in Australia, or something (tsk-tsk), this was not really cutting it for me.
  
Some quick googling led me to this forum post: [http://forums.pcpitstop.com/index.php?/topic/198236-why-is-my-skype-video-showing-upside-down/](http://forums.pcpitstop.com/index.php?/topic/198236-why-is-my-skype-video-showing-upside-down/)  
  
After making sure that the necessary packages was installed (notably libv4l-0) I adapted the command from the forum post to:  

```bash
LD\_PRELOAD=/usr/lib/i386-linux-gnu/libv4l/v4l1compat.so skype  
```

and voila, the image was OK.  
  
Next step is for this to be set to default, which seems to be outlined here (in steps 2 and 3): [http://pc-freak.net/blog/how-to-fix-upside-down-inverted-web-camera-laptop-asus-k51ac-issue-on-ubuntu-linux-and-debian-gnu-linux/](http://pc-freak.net/blog/how-to-fix-upside-down-inverted-web-camera-laptop-asus-k51ac-issue-on-ubuntu-linux-and-debian-gnu-linux/) (Actually this post seems to cover most of what is useful from the forum post above...)  
  
UPDATE (19/04/2013): Since my laptop was working fine, I decided it was about time to fix it. Also I wanted to use Cinnamon instead of Unity, as the latter had gotten more and more on my nerves. (A long story in itself.) I followed some instructions on how to get rid of lots of unwanted stuff and end up with something akin to a Lubuntu install. And lo and behold, it was nice... Until I started Skype today. The camera was topsy turvy again and the preloading of this .so from above resulted in an error. The file was missing. I found that I had the 64-bit version hanging around in a parallel folder and naively tried to load that instead, but alas, Skype seems to be a 32-bit beast, so that didn't work. The solution would be to (re)install the 32-bit libraries with:  

```bash  
sudo apt get install ia32-libs  
```

And the solution outlined above works like a charm again.