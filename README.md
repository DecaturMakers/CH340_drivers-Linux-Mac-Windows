# CH340 serial chip Drivers for [Linux](#linux), [Mac](#mac), and [Windows](#windows) all in one place
A One-Stop driver repo for the popular serial chip used on cheap Chinese Arduino clones.

The CH340G chip is a very popular USB to Serial chip used in Arduino clones because of its low cost. The OEM of this chip is Jiangsu Qinheng Co., Ltd. in the [Nanjing Software Valley of China](https://goo.gl/maps/WUmsK24bTDP2) according to [SparkFun](https://learn.sparkfun.com/tutorials/serial-basic-hookup-guide) who builds products that incorporate it.

![SparkFun Serial Basic](https://i.imgur.com/No5kyuy.png)

Unfortunately, [their website](http://www.wch.cn/download/CH341SER_MAC_ZIP.html), being entirely in Chinese, makes many people nervous. For this reason, there have been many people who have tried to be helpful by hosting a copy of the drivers on a more inviting site. However, that is a dangerous thing to be comfortable with. As a Maker Space that regularly teaches microprocessor hacking to beginners, [Decatur Makers](https://decaturmakers.org/) has decided to host yet another copy of these drivers. You may or may not trust us as a source, but we didn't feel safe sending our students elsewhere. We have done (and continue to do) everything in our power to verify and maintain the content of this repo.


# Installation

## Linux

The driver for this chip has been in the Linux Kernel [for a long time](https://github.com/torvalds/linux/commits/master/drivers/usb/serial/ch341.c). (Introduced in commit 6ce76104 that was released in Linux Kernel v2.6.24 Jan 24 2008) If your Kernel does not support this chip, you are probably very out of date and have severe vulnerabilities to worry about.

Even though **Linux users should never need this**, we're going to put the information here.

1. Download the [zip of this repo](https://github.com/DecaturMakers/CH340_drivers-Linux-Mac-Windows/archive/master.zip) and unzip it
2. Change into the directory that was created

    ```
    cd CH340_drivers-Linux-Mac-Windows/drivers/linux/
    ```

3. Compile the kernel module

    ```
    make
    ```

4. Load the kernel module

    ```
    make load
    ```

5. *If you need to* unload the kernel module

    ```
    make unload
    ```

* Source:
    * http://www.wch.cn/download/CH341SER_LINUX_ZIP.html
* SHA256 Checksums:
    * `5ba92d25345872b3aa72321b8b3bff0067b318a7b630087abb4b762e18df9624`  ch34x.c
    * `a47d44ae25907741a6f4a9b4e5fefd4f522f91159fe418de125b6eee05200681`  CH341SER_LINUX.ZIP


## Mac

**Warning:** Installation for macOS is [now] very simple. The internet is littered with links to unsigned drivers and out of date instructions telling you how to [recklessly] disable macOS security features that are in place to protect you from these kinds of things. Do not follow them! (If you have done this in the past, [undo it](https://developer.apple.com/library/content/documentation/Security/Conceptual/System_Integrity_Protection_Guide/ConfiguringSystemIntegrityProtection/ConfiguringSystemIntegrityProtection.html).)

### Recommended Install: via [Homebrew](https://brew.sh/)
I **really** suggest you install using homebrew. If you do not have `brew` installed, you should install it. It is the most common way to install things on a Mac that don't come from Apple's App Store.
1. Open the [Terminal](https://raw.githubusercontent.com/DecaturMakers/CH340_drivers-Linux-Mac-Windows/master/drivers/macos/Terminal.png) (use [Spotlight](https://www.imore.com/how-use-spotlight-mac#use) to find it if you must)
2. If you do not have homebrew, install it.

    ```
    /usr/bin/ruby -e "$(curl -fsSL https://github.com/Homebrew/install/raw/master/install)"
    ```

3. Install the driver. (You will be prompted for the password you use to log in to the Mac.)

    ```
    brew tap DecaturMakers/CH340_drivers-Linux-Mac-Windows https://github.com/DecaturMakers/CH340_drivers-Linux-Mac-Windows
    brew cask install wch-ch34x-usb-serial-driver
    ```

### Alternate Install:

1. Download the [zip of this repo](https://github.com/DecaturMakers/CH340_drivers-Linux-Mac-Windows/archive/master.zip) and unzip it
2. In Finder, navigate to `CH340_drivers-Linux-Mac-Windows-master/drivers/macos`
3. Open the file [CH34x_Install_V1.4.pkg](https://github.com/DecaturMakers/CH340_drivers-Linux-Mac-Windows/raw/master/drivers/macos/CH34x_Install_V1.4.pkg)
4. Follow the instructions in the installer

* Source:
    * http://www.wch.cn/download/CH341SER_MAC_ZIP.html
* SHA256 Checksums:
    * `032e85afc2dfeaba6e77637718749e3af381892305c2c02c12d1cd2bb3585bc3`  CH34x_Install_V1.4.pkg
    * `b190f612b833727b2006f362a835f7e97177b580e45cef253e164202106c48eb`  CH341SER_MAC.ZIP

## Windows

1. Download the [zip of this repo](https://github.com/DecaturMakers/CH340_drivers-Linux-Mac-Windows/archive/master.zip) and unzip it
2. In Windows Explorer, navigate to `CH340_drivers-Linux-Mac-Windows-master/drivers/windows`
3. Run either the 64bit or 32bit SETUP application

* Source:
    * http://www.wch.cn/download/CH341SER_ZIP.html
* SHA256 Checksums:
    * `543426ce41c8d5fa42aaa9885f8cd6c1132245a9552ee0e842b2993bae6ed224`  CH341SER.ZIP


# References
* https://kig.re/2014/12/31/how-to-use-arduino-nano-mini-pro-with-CH340G-on-mac-osx-yosemite.html
* https://forum.arduino.cc/index.php?topic=397368.0
* https://github.com/adrianmihalko/ch340g-ch34g-ch34x-mac-os-x-driver
