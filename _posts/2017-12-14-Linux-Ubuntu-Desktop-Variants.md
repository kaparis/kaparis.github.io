---
layout: post
title: "Linux - Ubuntu Desktops - Which one should you choose?"
date: 2017-12-14 00:00:00 -0000
comments: true
---

# Summary
I was intersted in getting a new linux distro. I know there are favorites out there, but I decided to go with Ubuntu which has been on top 10 lists for a few years at least and has a large user community. Ubuntu had switched to Unity being the default desktop, but recently announced switching back to Gnome. Considering I was going to go with the LTS version, Unity is still the default desktop. So I was intersted in trying out 2 other Ubuntu desktop variants of LXDE and XFCE. I will share my experience of installing the variants, what I learned, and what I ended up with.

# Info
* Linux Distro: Ubuntu
* Linux Distro Version: LTS 16.04.3
* Desktop: Unity
* Desktop: Lubuntu - LXDE
* Desktop: Xubuntu - XFCE


# Pre-Reqs
* Download ubuntu-16.04.3-desktop-amd64.iso
* Download lubuntu-16.04.2-desktop-amd64.iso
* Download xubuntu-16.04.3-desktop-amd64.iso

# Desktop Variants Details

* ubuntu-16.04.3-desktop-amd64.iso
    ISO Size: 1.6 GB
* lubuntu-16.04.2-desktop-amd64.iso
    ISO Size: 0.9 GB
    
    Note: Default ISO was for LTS 16.04.2 at time of writing

* xubuntu-16.04.3-desktop-amd64.iso
    ISO Size: 1.3 GB

# Install Experience
I installed the three Unbuntu variants in VMWare Virtual machines. I gave all VM same hardware definition of a single core CPU and 1GB of ram.

I started with Ubuntu Unity. When creating the VM, VMWare auto detected it was linux and offered quick install feature. So I was able to point to the ISO, and enter my default user id and password. Then VMWare created the VM and installed the OS without out any help needed by me. Really nice feature to get a OS up quickly. This also installed VMWare tools that let me resize the desktop on demand. When I loggeed in for the first time, VMTools weren't working yet. A quick logout and login resolved that. 

For Lubuntu, VMWare didn't auto detect it was linux. So I had follow the onscreen prompts to install. The only proablem I had was the next button in setup wasn't fully visible in the low resoluiton that VMWARE provides without VMWare Tools. I got around that by dragging the window to see the button. When I logged in for the first time, I had to install VMWare Tools to get the screen resize and other features. The tools were very easy to install. I did have to log out once and then log back in to activate VMtools after the install.

For Xubuntu, VMWare auto detected it was linux and offered quick install feature. So everything worked the same way the Ubuntu install did. Consistency, I love it.

# Considerations
My intent wasn't to make this my primary desktop. So I needed something that could run in a VM, small disk size for the OS, low memory, be very responsive, and have a terminal. So it had to play nice in my native environment OS of Windows 10. With these consideratiosn, I got some satistics of each install to help me evaluate which to use. I dome some experiments and my collected results are below.

## Ubuntu - Unity
OS Disk Space Used: 5.2 GB

Memory Used: 656 MB

xorg Memory Useage: 411 MB

Start Up Time to Desktop: 45 seconds

Time to Login to Desktop: 27 seconds

Total Time: 72 seconds

## lubuntu - LXDE
OS Disk Space Used: 4.1 GB

Memory Used: 221 MB

xorg Memory Useage: 256 MB

Start Up Time to Desktop: 45 seconds

Time to Login to Desktop: 38 seconds

Total Time: 83 seconds

## xubuntu - XFCE
OS Disk Space Used: 4.8 GB

Memory Used: 333 MB

xorg Memory Useage: 339 MB

Start Up Time to Desktop: 53 seconds

Time to Login to Desktop: 8 seconds

Total Time: 61 seconds

# Conlusion
The fastest startup time didn't surpize me. XFCE who's goal is to be light and minimal had the fastest boot time to the desktop, even if it had a longer start up time. I was surpized that Ubuntu Unity was able to get to the desktop faster than LXDE. 

The other surprize was LXDE had the least amount of Desktop memory usage instead of XFCE. I would of expected XFCE considering thats a goal of theres. I also was able confirm that Ubuntu Unity is a memory hog at 656 MB. Ubuntu Unity looks beautiful, but thats a large memory footprint.

I read that XFCE can be almost completly configed in the GUI, while LXDE still needs some configurations in files. I didn't confirms this, but the information was a deciding factor for me.

Given my three considerations, I will move forward with XFCE and see how running applications on there works for me. Linux has come a long way, and every year we all become proud of how good Linux has become. 
