RaspberryPi-for-Vision-Application-
===================================
Get know Raspberry Pi with python-openCV interface and its installation procedure.

Experience With RPI to share:
=============================

 Well working with Raspberry Pi is really awesome.I picked up a Raspberry Pi some months back without much of a need for it. Most of my electronics stuff is bought without a use, so I guess it's no surprise this time. I ended up ordering what is called the ModelB, which is the earlier model with 256MB of RAM. To be honest, I didn't really even know what the hell the board did, I just heard other tech ppls babble on about how it was going to revolutionize home computing. Since it's a full computer, not just a microcontroller.
  I have spent the past few months knowing this tech RPI and python full time, instead of just when I was told to work with some custom ARM boards for my college projects and where I was required to know enough mathematical interpretation of signal image computing algorithms in "C" to keep my project up and running. I've always liked Matlab cause of its highly computing ability with easy codebility. So for me it was really a point of attraction when I heard of python interpretor support for Raspbian OS.
  
Installation of OS on RPI:
==========================

 But now I had to find a way to tie my GPIO to my vision application. So the first step was to just install Raspbian. And it was so easy. As I'm using a Debian based OS, I also wanted a minimal installation. This leaves me with the Raspbian Installer(http://www.raspberrypi.org/downloads), which is essentially a Debian NetInstall built around Raspbian. Raspbian is available for free from the Raspberry Pi website. Under the header “Raspbian ‘wheezy’”, download either the torrent or direct download. The torrent has the potential to be faster, but some firewalls may block the required ports and you may have to use the direct download instead.
Once you have the ZIP file downloaded to your computer, unarchive it. There will be a single .img file inside. This is the disk image you will flash to the Raspberry Pi’s SD card. To install Raspbian, you will need an SD card that has 2 GB of space or more— this cheap 16 GB Class 10 SD card works great on the Raspberry Pi, and gives you plenty of room to add media and other programs once Raspbian is installed.

Installation of Raspbian image file on memory card:(check this is in Ubuntu..):

 Press Alt+Ctrl+T (shortcut for terminal)
 Go to the Terminal and type the following command, ensuring you replace the “[FILESYSTEM]” value with the one you noted earlier and the “[DISK IMAGE NAME]” with the proper file name obtained above.

sudo dd bs=1m if=[DISK IMAGE NAME] of=[FILESYSTEM]

For me, the command would look something like this:

sudo dd bs=1m if=2012-12-16-wheezy-raspbian.img of=/dev/rdisk4

Hit enter, and wait until the command completes. Once dd flashes the disk image, you can remove it from your Mac and plug it into your Raspberry Pi. The default username is "pi" and the default password is "raspberry".

 
 Perfect, just a barebones installation as soon as it finishes running.Then I got RPi outoff the enclosure, plugged it with HDMI to VGA converter, which was able to connect monitor of my PC. Than I plugged  my USB keyboard and sat down for a quick install. Except, the RPI doesn't seem to want to respond to my keyboard. A quick overview of what I was doing revealed that my keyboard was actually an un-powered USB device. The RPi isn't powerful enough to run it as minimum 500mA current was required for its own processing. Great. Luckily I had my mobile charger with higher rating, I can use to send enough power to the keyboard. Which then did work than.

