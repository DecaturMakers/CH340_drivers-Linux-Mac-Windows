# CH34X USB-SERIAL DRIVER INSTALLATION INSTRUCTIONS

Version: V1.0

Copyright (C) Jiangsu Qinheng Co., Ltd.

## Support System:
OS X 10.9 and above

## Installation Process:
1. unzip the file to a local installation directory
2. Double-click CH34x_Install.pkg
3. Install according to the installation instructions
4. Restart after finishing installing

After the installation is completed, you will find serial device in the device list(`/dev/tty.wchusbserial*`), and you can access it with serial tools.

If you can’t find the serial port , you can follow the steps below:
1. Open terminal and type ‘ls /dev/tty*’ and then you will see devices like tty.wchusbserial;
2. Open ‘System Report’->Hardware->USB, the right side is “USB Device Tree” there will be device named “Vendor-Specific Device” and check if the Current is normal.

![screenshot 1](https://github.com/DecaturMakers/CH340_drivers-Linux-Mac-Windows/raw/master/drivers/macos/1.png)

If the steps below don’t work at all, please follow the installation steps and try again.

Note:
1. Please enter “System Preferences”->”Security & Privacy”->”General” page, below the title ”Allow apps downloaded from:” you should choose the choice 2->”Mac App Store and identified developers” so that our driver will work normally.

![screenshot 2](https://github.com/DecaturMakers/CH340_drivers-Linux-Mac-Windows/raw/master/drivers/macos/2.png)


2. If old version of unsigned driver is now existing in your PC, please uninstall it first. Open Application “Terminal” and type commands below step by step:
<1> “sudo su” and input your password;
<2> “rm -rf /System/Library/Extensions/usbserial.kext”; <3> If you cannot find the kext in step2, please try to type:
“rm -rf /Library/Extensions/usbserial.kext”;
