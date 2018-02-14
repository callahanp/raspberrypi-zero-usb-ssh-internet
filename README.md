# raspberrypi-zero-usb-ssh-internet
Documentation, Scripts and Instructions for connecting a Raspberry Pi to a PC/Mac/Linux host for access to the pi by ssh and access to the internet from the pi.

Feb 15, 2018 - I'm not working on this at this time. No-one else seems interested in working on it. There may be better ways to approach the problem anyway so this project may be deleted. It's not at version 0 yet, but you are welcome to take a look at the script and comment or laugh.

On March 10, 2018, I'll be working on a raspberry pi cluster project that boots over usb. No sd card required. With this approach, its' not necessary to get the zero on the internet in order to update the os. That's all done on the root machine, whether its a raspberry pi or something else.

 The approach to creating a cluster taken here works well: https://www.raspberrypi.org/forums/viewtopic.php?f=49&t=199994  I'll be adapting it so custom software runs on each node in the cluster.


**Goals:**
* While still in  Linux, Windows or MacOS Customize and Configure a Raspberry pi SD Card

 * Use a USB RNDIS connection with dwc2 and g_ether drivers
 * Static Mac address
 * Static IP address, Gateway IP address and DNS IP addresses

* Custom Pi Hostname with id numbers to distinguish each pi

* Configure additional Pi units with the same or "next" Mac and IP addresses

* Extra Features:
 * Additional Accounts
 * Enable SPI and I2C

[See the github wiki for this project for more information] https://github.com/callahanp/raspberrypi-zero-usb-ssh-internet/wiki
