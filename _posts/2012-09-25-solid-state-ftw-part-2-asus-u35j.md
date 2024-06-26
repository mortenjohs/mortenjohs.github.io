---
layout: post
title: 'Solid State FTW - Part 2: Asus U35J'
date: '2012-09-25T20:12:00.000+02:00'
author: Morten
tags:
- Linux
- SSD
- Hardware
- Ubuntu
- Upgrade
- Windows 7
modified_time: '2012-09-25T20:12:23.295+02:00'
blogger_id: tag:blogger.com,1999:blog-6967032375013519080.post-7832099350298772210
blogger_orig_url: https://m635j520.blogspot.com/2012/09/solid-state-ftw-part-2-asus-u35j.html
cover-img: http://farm8.staticflickr.com/7234/7328717020_2f2cd4c6e1.jpg
thumbnail-img: http://farm8.staticflickr.com/7234/7328717020_2f2cd4c6e1.jpg
share-img: http://farm8.staticflickr.com/7234/7328717020_2f2cd4c6e1.jpg
---

[![Shellac @ L'épicerie](http://farm8.staticflickr.com/7234/7328717020_2f2cd4c6e1.jpg)](http://www.flickr.com/photos/mortenjohs/7328717020/ "Shellac @ L'épicerie by mortenjohs, on Flickr")  

Inspired by the [success of the new SSD in my Mac Pro](https://blog.ervik.fr/2012-09-22-solid-state-ftw-part-1-mac-pro-early/) (and puzzled by a weird HD error) I went ahead and invested in a SSD for my 2010 Asus laptop as well.

To get everything up and running the way I wanted took a bit more hacking than with the Mac, but now everything seems great - dual-booting Ubuntu 12.04 (main OS) and Windows 7 (mainly for gaming - till Steam is launched for Linux). This is what I did.  
  
I went for a 128 Gb CRUCIAL SSD m4 2,5" with a noname external 2,5" drive case. I tore out the old 600Gb-ish drive from the laptop, put it in the external case, and fit the new drive in its place. "Klok av skade", I went for installing windows first. (The Windows 98 installer overwrote my SuSE back in the day...)  

#### Windows 7

Since this Asus doesn't have an optical drive, I couldn't generate the "Recovery disc(s)" needed to reinstall the operating system. (Clever Asus.) The way I got around that was to boot Ubuntu 12.04 from a USB-stick, used gparted to partition the SDD (with a primary partition, a logical, and a linux swap one) and copy the recovery partition from the (now) external drive to the first partition on the SSD drive. Afterwards I rebooted holding F9 to launch the recovery. And it worked! (It took me a while to realize that I had to hold down F9 even though the recovery partition booted (because it was the only partition there), but failed to install without this magic button.) I asked the windows installer to use the whole HD (leaving the recovery partition be). After some time and a gazillion reboots I had a windows install up and running (full of Asus bloatware - but that is for another post).  
  
Some additional points:  

*   Ninite is your friend. [http://ninite.com/](http://ninite.com/)
*   So is Railsinstaller. [http://railsinstaller.org/](http://railsinstaller.org/)
*   I'm considering putting Steam games on an external HD and symlinking to them... (For now I have just installed the most important ones - CivV, Bastion, Frozen Synapse, and SpaceChem on the SSD.) Savegames are already symlinked to a Dropbox-folder.

#### Ubuntu 12.04

I replaced the 20 GB recovery partition from the step above with Ubuntu. Easy peasy. Booted from the USB stick. Installed.  
  
Some points:  

*   Boots grub to login in less then 6 seconds.
*   Most things (that I have tested) works out of the box.

*   Two-finger scrolling needs to be set up in the Mouse Preferences.

*   I don't use the nvidia-card, just the intel one - to save battery, since anyway, I don't plan to game on the linux part of the laptop. (Till Steam releases their Linux client.)
*   Sleep works, hibernation doesn't. (Not really a problem, methinks.)

#### Common

I keep my dropbox files in one place and have added some symlinks in both OSs to link to them.