---
layout: post
title: "Linux on a USB Stick - Direct Boot and Running in a Virtual Machine the same Linux Environment"
date: 2018-10-04 00:00:00 -0000
categories: development
comments: true
---

# Summary
I have been running a Linux virtual machine, with the virtual disk on a USB stick for a while as my main development environment. Running a VM on my harddisk impacted performance of my windows machine (I don't have a SSD), so I run it off a USB stick which worked nicely. I at times wanted to boot directly into my linux environment to leverage the full performance of my laptop. I also move around various computers, so haveing the portablility to use any computer and resuming work was something I desired. Thats when I looked into the options of how to do this.

# My Criteria
* Be able to run my Linux off the USB by booting into it, thus bypassing my computers default OS. (Leverage full CPU and RAM)
* Be able to run my Linux environment on the USB in a virtual machine when I didn't boot into it
* Be able to reserve some space off to the side for Windows based file shareing.

# Requirements
* Ubuntu 18.X LTS  (I used the xbuntu version)
* VMWare Workstation
* Linux Live USB Creator 
* 2x 8GB USB stick

# My Journey
The first apporach I treid was the Linux Live edition persistence. This worked nicely, I could boot from the USB on my physcical PC or from a virtual Machine. Everything loaded into RAM and persistence option gave me some flexability to save files and change packages. However, I had to choose on boot every time the live edition or to install, I had no user account to log in, and major changes to the system could break the live edition. I quickly elimated this as a choice

My second approach was to install the full edition of Linux on the USB stick. This is perfectly allowable action to take. I could then boot directly into Linx at the boot menu. I could do that on a physical PC or in the virutal machine boot menus. Now I am making some progress. I'm able to accomplish 2 of my Criteria. I learned about another trick, where I can attach a physical disk to my Virtual Machine and boot into it. Its strait forward, you create a virtual machine, but instead of createing a virtual disk to reside on your real disk, you point the virtual disk to a physical disk.  

I need to take one more step. How could I save the virutal machine files and my aux files on the USB stick to use in windows? I decided to partition the USB stick into to pieces. A Linux partiion and my windows partiion. Then I installed Linux on one partition, and in the other I used for files. 

## Create a bootable USB stick with Linux Live
1) Download the Linux ISO of your choice. I choose xubuntu-18.04.1-desktop-amd64.iso
2) Use Linux Live USB Creator to create a live edition. Will use this in the next step to install Linux on our final USB Stick.
3) You now have a USB stick that can boot into Linux Live.

Note: You could of just burned a CD with Linux Live

## Create the USB stick with full Linux installed
1) Boot into your newly created USB stick
2) Choose the Install Option
3) Installation Type, Choose "Something Else" to be able to choose your own partition tables
4) I'll assume a brand new usb stick, meaning we can wipe it clean. I choose the below table as my partition setup. You will notice no swap and no home partiions. I was installing on a small 8GB USB stick and decided that was ok for me. I created a small windows partition for files I wanted to share between Linux and Windows. Linux sees FAT32 partitions, but Windows doesn't see EXT4 partitions; so it made more sense to format as FAT32 for cross platform sharing.

### Partitions

| Partition    | Notes | 
|--------------|-------|
| / windows    | Partition that contains window files |
| / root       | root, were Linux will be installed   |

Note: Xbuntu 18.x installs with a footprint of ~4,500 MB

5) Linux didn't format my windows FAT32 partition. So before windows can use that partition, we need to format it. I used Windows disk managment to format the partition. Then Windows could see my partition. The next problem I had was everytime I plugged in the USB stick, Windows asked me to format the Linux partition. So I ussed MiniTool Parition Wizzard to set the partition to hidden. After that, windows doesn't see the linux partition, and doesn't prompt you to format the partition eithier.

## Setup VMWare Virtual Machine to boot Linux

### Option A - Vmware
Unlike on a MAC, there is no smooth way to boot from a physical disk and virtual machine. The approach I found to to be best is to have VMware station boot from the USB stick. You have to take some steps to get it to work, as booting directly from USB in VMWare is not its strong suite. The disadvantage is that VMmware unmounts the USB stick from Windows. Which meant I couldn't have the VMWare files reside on the USB stick, and instead had to reside on Windows. However its for the best becausing having your native OS and VMware write to the same partition can result in coruption of your data.

1) Create a new virtual machine. You can create a small disk, but we won't use it.
2) After creating the VM, goto VM-Settings-Options-Advance and change the Firemway Type from BIOS to UEFI. This will let us boot from USB. BIOS won't let us boot from USB.
3) VMware wasn't detecting my USB stick at first. After I disconnected the USB stick and reconnected, USB showed up a boot option in my list.
4) Go into the setup, and change boot order to have EFI USB Device as first boot device. This will save you step to select the boot device on start.


This is where I got stuck. VMware just wouldn't book my USB stick. I tried some alternatives but in the end it didn't work out. EFI didn't want to boot my USB device. May be related to support of USB 3.0 in EFI in VMware. I don't really know. I also tried direct link to physical drive using VMware setting, but that also didn't work. 

# Conclusion
I meet 2 of 3 of my criteria. Sadly, I failed in my third criteria. I'm sure if worked on it somemore, I could of figured out a way to make it work. I ended up sticking with my virtual machine only approach to development. At least I'm able to take my Linux environment with me anywhere VMPLayer is installed.