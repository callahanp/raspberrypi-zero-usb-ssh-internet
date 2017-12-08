# raspberrypi-zero-usb-ssh-internet
Scripts and instructions for connecting a Raspberry Pi to a PC/Mac/Linux host for access to the pi by ssh and access to the internet from the pi

Like many on this thread, I've been puzzling through the various bits of information and howto pages on connecting a raspberry pi through USB using the g_ether driver, dwc2 and the RNDIS protocol. At this point I can ssh from Linux to the Pi. One problem with this is that when I boot the Linux box and the PI together, the MAC address is not the one I configured on the Pi. So for Now I'm powering up the Pi after Linux is up and running. The other problem is a lengthy amount of time spent in network manager, possibly waiting for the pi connection to resolve.

There's a large number of posts on this forum and many others with questions and partial answer to the problem of connecting a Pi-Zero via USB.

Here's the problem in a nutshell:

We need ssh access to the PI-Zero AND we need access to the internet from the pi-zero at the same time. We want the connection to be automatic, and to not require re-configuration after each boot. While this is almost trivial for Pi models with Ethernet or wireless features, it's not so easy for the Pi-Zero.

I'd like to form a team willing to work on properly documenting ssh and a working Pi internet connection for the special case of a PI-Zero.

I'd want to end up with not just a cookbook of configuration details, but information on the underlying technologies and software. I'd like to know what the configuration details actually do to make the connections work on each platform. While there's lots of configuration specifics out there for the Pi-Zero, There's little information about how these connections work behind the scenes and the differences making the connections on different Operating Systems.

Any takers? If you want to work on this with me, contact me through the forum by sending me an e-mail. Click on callahanp at the right.

- Pat Callahan
Dec 2017
Masschusetts USA 

Here's what I'm looking for on each platform: Linux, MacOS, Windows. 

In general, I want information on every aspect of the connection between the pi, the box running ssh and the internet. This includes not just configuration items, but the software pieces that use the configuration item or otherwise process the IP packets. I want information not just on how the software sets up a connection but what the software does during an exchange of IP packets.

On the PI:
* What drivers are loaded to make the connection to the PI. What causes them to load, When they are loaded and what specific configuration items do they use. What exactly are dwc2 and g_ether? Are they configured? How? When?
* When and how is the Pi's MAC address on the USB connection determined 
* Why booting the pi and my linux box at the same time gives me different MAC addresses even though the Pi is configured with a static MAC address.
* How and when does the Pi gets its IP address, Gateway IP address and DNS information when making the USB connection.
* How and when does the Pi get its host name.

On the box running ssh
* What drivers are loaded to make the connection to the PI. What causes them to load, When they are loaded and what specific configuration items do they use. What are Bonjour and Avahi and what specifically do they do with configuration items? How are they involved in a connection over USB or the internet.
* How to delay the connection so the PI determines the MAC for both ends of the USB connection.. 
* How to ensure that the IP packets for Internet connections on the PI make it from and to the PI.
* How does the USB connection get it's IP address. Is anything else needed to make the internet connection.
* How does routing work with a USB connection.
* Can we configure a specific host name for the PI, without using .local
* Can we ssh to raspberrypi.local and still get to the internet from the pi?

PI-Zero <--> software/config? <--> USB Port <--> Cable <--> USB Port <--> software/config? <--> usbx* <--> software/config? <--> SSH

PI-Zero <--> software/config? <--> USB Port <--> Cable <--> USB Port <--> software/config? <--> usbx* <--> software/config? <--> The Internet

* as seen in ipconfig or ifconfig

see: https://www.raspberrypi.org/forums/viewtopic.php?f=63&t=168285&p=1243329#p1243329
