---
layout: post
title: ""
description: "Implementation - Monitor Installation"
background: '/img/bg-post.jpg'
---
<link rel="stylesheet" href='{{ '/assets/post-entry-style.css' | prepend: site.baseurl | replace: '//', '/' }}'>  
  
This post follows on the [Getting Started Design](/2019/06/30/design-getting-started.html) post.

# First Interaction
The first interaction is with the Firebase RT db.  As noted in the design post, one of the steps we take to initiate the FitHome experience is to make a pre-member entry into the Firebase RT db.
![pre-member db entry](/assets/post-imgs/post-2019-6-30/pre-members-db.png)  
  
We make this entry prior to the electrician installing the energy monitor.
# Configuring the Monitor
The monitor needs two pieces of information:  
* The machine name.  This is configured "hard coded" into the firmware.  The machine name is a combination of a common name followed by a '-' and then the date.  For example, the machine name in the above image is ```bambi-07012019```. The common name is bambi and the date is 7/1/2019. 
* The SSID/password of the homeowner's wifi.
Ideally, the SSID/password would magically vaporize into the energy monitor when the electrician plugs it in.  Unfortunately, it does not.
## Configuring wifi
Soon after the electrician installs the energy monitor, the home owner must tell the energy monitor the home wifi SSID and password.  The technique to do this is starting the energy monitor's firmware as a Local Access Point.  We discuss the details within the code for [the energy monitor firmware](https://github.com/BitKnitting/energy_monitor_firmware)
  
After successful completion, the energy monitor is able to use the home's wifi.
# Sending Readings
Now that the energy monitor is online, it will start sending power readings to the Firebase RT db over wifi.  The details are discussed within [the energy monitor firmware](https://github.com/BitKnitting/energy_monitor_firmware) Readme file.