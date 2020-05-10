---
layout: post
title: What I've learned about running Linux
date: 2020-03-29 15:55:23 -0500
tags: [linux]
image: ubuntu-logo.png
---

Linux operating systems are an excellent choice for people in a variety of situations, and there are a number of options for how to run them.  I gained some experience with this while starting out on TheOdinProject curriculum several months ago, and would like to share my own observations and recommendations about trying Linux and potentially installing one of its distributions as your primary OS.

First off, Linux is the a broad term that refers to the Linux kernel - the core component that approximately 600 distributions are based on.  I wanted to run Linux because there are a wide variety of applications available free of charge, which are essential to me as a coder.  A lot of the work I do in Linux is done on the command line, which is a powerful way of interacting with the computer.  

![Ubuntu Logo](/assets/img/ubuntu-logo.png)

There are a wide variety of Open Source Linux distributions to choose from, but my current favorite is Ubuntu, which is what this post will focus on.  Ubuntu is one of many free distributions, and its widely used.  Ubuntu is maintained by its users, who work hard to keep it running smoothly and resolve bugs in a flash.  In summary, these are the things I like about Ubuntu:
  * It's free
  * Intuitive Graphical User Interface (GUI) 
  * Strong Community Support
  * Less likely to be targeted by hackers

If you're interested in taking Ubuntu for a "test drive" without doing any big software installations on your system, you're in luck!  Ubuntu let's you create a bootable USB for this purpose, and they have an excellent [step-by-step tutorial](https://ubuntu.com/tutorials/tutorial-create-a-usb-stick-on-windows#1-overview) on how to do it.

So, once I created my bootable USB, I knew Ubuntu was going to be my go-to OS as a coder.  But I knew there were a few options for how to permanently install it:
  * Dual-boot with Windows: This involves partitioning your hard drive to run Windows and Ubuntu on the same computer.  Every time you boot up, you are prompted with a menu where you select which OS you would like to run.

  * Install Ubuntu as a Virtual Machine: This involves downloading a free program in Windows called [VirtualBox](https://www.virtualbox.org). You then run VirtualBox it will let you create a virtual machine that runs Ubuntu (or many other operating systems) while you run Windows. In other words, once installed, you boot up Windows and within Windows, there will be a "window" within which Ubuntu will boot-up.
  
  * Straight install of Ubuntu: Simply install Ubuntu as the sole operating system on a computer's hard drive.

I decided to dual-boot Ubuntu, since I was not ready to cut the cord to my longtime apps available in Windows, and didn't like the little bugs or configuration issues that come with running a virtual machine.  I was using a really old laptop that was in rough shape, so I decided this was my excuse to upgrade to a newer computer.  My experience was that setting up a dual-boot is a challenging and time-consuming job for a novice, but a good learning experience.  A good step-by-step guide on this process is availalbe at [It's Foss](https://itsfoss.com/install-linux-in-virtualbox/).

If running Windows and Ubuntu on the same machine are important to you, I'd highly recommend dual booting if you have the patience to do it properly.  If you are using a computer that has important files saved on its hard drive, it's essential that you back up those files before starting the process.  It took me a bit of trial and error before I successfully set up my system the way I wanted it.

Another great alternative would be to use an older laptop or desktop computer.  Computers that aren't snappy enough with Windows often do very well with Ubuntu, which is much more efficient with using your system resources.  So, either using an old computer you already own, or acquiring a used one might be great ways launch your Ubuntu experience on a budget.  Please leave a comment about your experience installing Ubuntu or another Linux distribution on your computer.