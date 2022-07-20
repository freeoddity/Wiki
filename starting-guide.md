---
layout: page
title: Starting-Guide
permalink: /starting-guide/
nav_order: 1
---

---

## **Getting Started**

**DISCLAIMER: Dokkan Entropy is currently in beta and limited to beta-testers.**
[If you'd like to become one simply join the discord and become verified.](https://discord.gg/3j9PpUgPFJ)

First you'll need to sideload the [**IPA**](https://discord.com/channels/961349987059531928/962947129935024128/994886846146428988) onto your device. There are numerous way's to do this. Some sideloading services are listed below.
 - [**Sideloadly**](https://sideloadly.io/) **Has a 100% success rate with Entropy**
 - [**AltStore**](https://altstore.io/) **Currently Not working properly with Entropy. We're working on resolving this issue**
 - [**Signulous**](https://www.signulous.com/)

Next you'll need to install the [**Dokkan Entropy Server**](https://discord.com/channels/961349987059531928/962947129935024128/994886846146428988) onto your Desktop or Laptop. Currently there is only a Windows Build but builds for Mac and Linux will be released soon!

Upon completing the Discord Authorization. You'll need to restore or create a bot account. Currently Entropy uses this bot account to grab the assets from the offical servers. When the patching portion of Entropy is complete we will remove the dependency on the offical servers.


**DISCLAIMER: With iOS 14 Apple introduced Local Network Permissions. If you're connecting your phone to your local machine (A PC/Laptop running on your home wifi) Then you will need to enable Local Netowork Access to the Entropy App on your phone. The switch can be found in the app Settings.**
[**There is a local network bypass but it's advised to use this at your own risk**](/lnbypass.md)

![**localnetoworkpng](/imgs/LocalNetwork.png)

Once the main menu loads you'll have a slew of options to customize your server. If you'd like to start playing immediatly then hit `[1] Start Server`. The program will prompt you to choose a port or hit enter to continue on the default port which is 8080. If you do choose another port then the program will make your chosen port the new default port. It should look like this.
!["Entropy Server Port Question"](/imgs/PortQuestion.png)

After choosing the port the program will give you an ip address and port number.

Now on your idevice go to the Settings app, scroll down until you find Dokkan Entropy or Whatever name you've given the sideloaded app and select it then select Entropy PC settings. There you'll see two textfields labeled Hostname and Port.
!["wheresPCgif"](/imgs/wheresPC.gif)


**DISCALIMER In the gif example above I am using the local network bypass mentioned earlier.**

Enter `http://server_ip` into the hostname field. Replace `server_ip` with the ip given to you by the Dokkan Entropy server. It's advised to double check and make sure the ip given by Entropy is the same ip given when you run `ipconfig` in a terminal. If they're are not the same. Then you should use the ip given by `ipconfig` the server is designed to run on `0.0.0.0` so it will respond to any incoming connections. You can also use `http://your.domain.com` if you have a registered domain resolving to your machine or vps. If you'd like to support https then on Entropy server hit `[6] Edit Settings`
then `[8] Change HTTPS Status`. If the current status is 0, then https is disabled. If it is 1 then it is enabled.

Enter the same port number you entered when starting the server into the port field.

Finally you can start the app and you should go though the initial data download. After you'll be at the dokkan main menu awaiting adventure!


