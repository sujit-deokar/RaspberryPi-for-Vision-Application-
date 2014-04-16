RaspberryPi-for-Vision-Application-
===================================
Get know Raspberry Pi with python-openCV interface and its installation procedure.

Experience With RPI to share:
=============================

 Well working with Raspberry Pi is really awesome.I picked up a Raspberry Pi some months back without much of a need for it. Most of my electronics stuff is bought without a use, so I guess it's no surprise this time. I ended up ordering what is called the ModelB, which is the earlier model with 256MB of RAM. To be honest, I didn't really even know what the hell the board did, I just heard other tech ppl babble on about how it was going to revolutionize home computing. Since it's a full computer, not just a microcontroller.
  I have spent the past few months knowing this tech RPI and python full time, instead of just when I was told to work with some custom ARM boards for my college projects and where I was required to know enough mathematical interpretation of signal image computing algorithms in "C" to keep my project up and running. I've always liked Matlab cause of its highly computing ability with easy codebility. So for me it was really a point of attraction when I heard of python interpretor support for Raspbian OS.
  
Installation of OS on RPI:
==========================

 But now I had to find a way to tie my GPIO to my vision application. So the first step was to just install Raspbian. And it was so easy. As I'm using a Debian based OS, I also wanted a minimal installation. This leaves me with the Raspbian Installer(http://www.raspberrypi.org/downloads), which is essentially a Debian NetInstall built around Raspbian. Raspbian is available for free from the Raspberry Pi website. Under the header “Raspbian ‘wheezy’”, download either the torrent or direct download. The torrent has the potential to be faster, but some firewalls may block the required ports and you may have to use the direct download instead.
Once you have the ZIP file downloaded to your computer, unarchive it. There will be a single .img file inside. This is the disk image you will flash to the Raspberry Pi’s SD card. To install Raspbian, you will need an SD card that has 2 GB of space or more— this cheap 16 GB Class 10 SD card works great on the Raspberry Pi, and gives you plenty of room to add media and other programs once Raspbian is installed.

Installation of Raspbian image file on memory card using Ubuntu:

 Press Alt+Ctrl+T (shortcut for terminal)
 Go to the Terminal and type the following command, ensuring you replace the “[FILESYSTEM]” value with the one you noted earlier and the “[DISK IMAGE NAME]” with the proper file name obtained above.

sudo dd bs=1m if=[DISK IMAGE NAME] of=[FILESYSTEM]

For me, the command would look something like this:

sudo dd bs=1m if=2012-12-16-wheezy-raspbian.img of=/dev/sdb

Hit enter, and wait until the command completes. Once dd flashes the disk image, you can remove it from your Mac and plug it into your Raspberry Pi. The default username is "pi" and the default password is "raspberry".

Installation of Raspbian image file on memory card using Windows:

The recommended method for flashing an SD for use in a Raspberry Pi is a program called Win32DiskImager. The latest version can be found on the official website(http://sourceforge.net/projects/win32diskimager/files/). Once you’ve downloaded the Win32DiskImager application and extracted the ZIP file, download the Raspbian distribution. This can be found on the Raspberry Pi website(http://www.raspberrypi.org/downloads) under the heading “Raspbian ‘wheezy’”. Once the ZIP file downloads, extract the .img from the .zip.
     In Win32DiskImager, ensure you select the correct drive letter for your SD card. Also, select the .img file you extracted from the Raspbian distribution above using the file picker. Once you have made sure you have the correct .img file and drive letter for your SD card, click “Write” (not read) to flash the SD card. This will take less than five minutes on average and you can see the current progress in the Win32DiskImager window. Once the flash completes, you can exit the program. 

 Perfect, just a barebones installation as soon as it finishes running.Then I got RPi outoff the enclosure, plugged it with HDMI to VGA converter, which was able to connect monitor of my PC. Than I plugged  my USB keyboard and sat down for a quick install. Except, the RPI doesn't seem to want to respond to my keyboard. A quick overview of what I was doing revealed that my keyboard was actually an un-powered USB device. The RPi isn't powerful enough to run it as minimum 500mA current was required for its own processing. Great. Luckily I had my mobile charger with higher rating, I can use to send enough power to the keyboard. Which did work than.

Setting internet on RPi:
==========================
Internet on RPi can be set using dynamic (DHCP) or static (IP) settings:
To configure the board to use DHCP or static IP settings:

    You can use a LXTerminal to access DHCP settings.

    Display the contents of the /etc/network/interfaces file. Enter:

    cat /etc/network/interfaces 

1) If the board is configured to use DHCP services (the default configuration), dhcp appears at the end of the following line:
If the board is configured to use static IP settings, static appears at the end of the following line:

    iface eth0 inet static

    To use DHCP services, change the line to:

    iface eth0 inet dhcp
   Press Ctrl+X.
   Enter Y to save the modified buffer.
   Now , disable the interface,
   ifconfig eth0 down
   Enable the interface,
   ifconfig eth0 up 
   Display details of all interface,
   ifconfig -a

2) To use static IP settings, change the line to:

    iface eth0 inet static

    For static IP settings, add lines for address, netmask, and gateway. For example:

 iface eth0 inet static
 address 10.0.0.20
 
 netmask 255.255.255.0
 
 network 10.0.0.0 //I didn't enter this line
 
 broadcast 10.0.0.255 //I didn't enter this line
 
 gateway 10.0.0.10

        Press Ctrl+X.
        Enter Y to save the modified buffer.
now go for:

sudo reboot
