---
layout: post
title: ""
description: "Implementation - Monitor Installation"
background: '/img/bg-post.jpg'
---
<link rel="stylesheet" href='{{ '/assets/post-entry-style.css' | prepend: site.baseurl | replace: '//', '/' }}'>  
  
This post follows on the [Design - Getting Started](/2019/06/30/design-getting-started.html) post.

# First Interaction
Our first interaction with the Fithome system is with the Firebase RT db.  As noted in the design post, one of the steps we take to initiate the FitHome experience is to make a pre-member entry into the Firebase RT db.  
![pre-member db entry](/assets/post-imgs/post-2019-6-30/pre-members-db.png)  
  
We make this entry prior to the electrician installing the energy monitor.
# Configuring the Monitor
Prior to the electrician installing the energy monitor and CTs, we have configured the machine name and Firebase Project ID within the config.json file for the microcontroller.  How this is done, including how the home owner's wifi SSID and password are discussed within the [energy monitor firmware Readme file](https://github.com/BitKnitting/energy_monitor_firmware/blob/master/Readme.md).

# Sending Readings
Now that the energy monitor is online, it will start sending power readings to the Firebase RT db over wifi.  The details are discussed within the [energy monitor firmware Readme file](https://github.com/BitKnitting/energy_monitor_firmware/blob/master/Readme.md).