---
layout: post
title: ""
description: Testing Current of Rev B Power PCB
background: '/img/bg-post.jpg'
---  
<link rel="stylesheet" href='{{ '/assets/post-entry-style.css' | prepend: site.baseurl | replace: '//', '/' }}'>

[Power PCB GitHub](https://github.com/BitKnitting/FitHome_Power_PCB).  In particular, the Current Samplig section of Readme.md.
# Test 1 - 0 < I1P_0_IN <= 600mV Vpp 
I used my nifty-difty power cord current measuring thing and strapped the CT around the power line.
![power cord thingy]({{'/img/power_cord_thingy_with_clamp.jpg' | prepend: site.baseurl | replace: '//', '/' }})    
I connected my soldering iron to this and turned on the power.  

Not working.  I tried Tisham's board, using a DMM set to VAC.
Put one probe on IA1+ and the other probe on GNDA.  I got a reading of 15mV.
As with yesterday's test, I soldered the small additions required for Current Sampling from U1.  Questions:  
* Have I correctly identified the pins on the TRS 3.5 Jack's layout to the rings on the CT?  After all, I "custom made" the layout.  

Go back make sure understand.


## Results
