---
layout: post
title: ""
description: Testing VP0 of Rev B Power PCB
background: '/img/bg-post.jpg'
---  

[Power PCB GitHub](https://github.com/BitKnitting/FitHome_Power_PCB)
# Test 1 - VP0 ~= 135mV
_Note: Why 135mV is discussed within the Power PCB's GitHub Readme file_  
I soldered just enough of the components to take a reading.
## Wire colors
I always forget which colors are power and which are ground on a cable.  So I copy around:  
## Color coding of power lines in power cord
```
| Function 	| label 	| color 
|----------	|-------	|-------
| Neutral  	| N     	| white 
| Line 1   	| L1    	| black 
| Line 2   	| L2    	| red   
| Ground        | G             | green   
```
## What the PCB looks like
### Front
![board front]({{'/img/revB_Power_PCB/vp0_test_board_front.png' | prepend: site.baseurl | replace: '//', '/' }})
### Back
![board back]({{'/img/revB_Power_PCB/vp0_test_board_back.png' | prepend: site.baseurl | replace: '//', '/' }})
## Results
Ooh. Yippee!    
![VP0 under scope]({{'/img/vp0.bmp' | prepend: site.baseurl | replace: '//', '/' }})  
VP0 = 143. Without knowing better, I'm saying close enough...