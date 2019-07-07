---
layout: post
title: ""
description: "HW/FW - Energy Monitor"
background: '/img/bg-post.jpg'
---
<link rel="stylesheet" href='{{ '/assets/post-entry-style.css' | prepend: site.baseurl | replace: '//', '/' }}'>  
# Electricity to our Homes
## Electricity Coming Into Our Homes
 In our North American homes, 120V of electricity comes in through two power lines (HOT1 and HOT2).  
 ![power lines](/assets/post-imgs/post-2019-07-03/Power_wires_coming_into_house.png)  
To measure the current, we use two Current Transformers (CTs), one for each power line.  To measure the voltage, we use readings from an AC power transformer plugged into our energy monitor.

# Hardware
## Energy Monitor
We are using Circuit Setup's [Split Single Phase Real Time Whole House Energy Meter](https://circuitsetup.us/index.php/product/split-single-phase-real-time-whole-house-energy-meter-v1-2/) as the "brains" behind getting the readings from the home.  
![energy meter](/assets/post-imgs/post-2019-07-03/energy_meter1.jpg)  
  
## Current Transformers
The electrician snaps one CurrentTransformer (CT) over each of the home's two power lines.
### Characteristics of the CT
 The characteristics of a CT to be considered when sourcing include:
 * The amount of Amp Service.  This is important because it dictates the hole diameter of the CT.  Many homes are wired for 100 Amp service.  As a homes electricity use increased, the service increased to 200 Amps.[From this article _Understanding Your Home's Electrical Load_](https://www.bhg.com/home-improvement/electrical/how-to-check-your-homes-electrical-capacity/) _Different homes need different amp services. A 60-amp service is probably inadequate for a modern home. A 100-amp service is good for a home of less than 3,000 square feet that does not have central air-conditioning or electric heat. A home larger than 2,000 square feet that has central air-conditioning or electric heat probably needs a 200-amp service._  According to [Bill Thompson of the Open Energy Monitor Project](https://community.openenergymonitor.org/t/ct-hole-diameter-for-north-america/5149), _US homes built before the late 60s were wired with Copper and typically had 100 Amp service, which used AWG 0 copper...Sometime in the late 60s to early 70s, Copper Service Entrance Wires were replaced by Aluminum. Since Aluminum has more resistance per foot than Copper, the equivalent Aluminum wire is two gauges larger than its Copper counterpart. About that same time, 200 Amp service became the norm._  
 * The wire gauge.  The Outside Diameter of the wire gauge determines how large the diameter of the CT clamp must be.  As Bill noted, wires could be copper or aluminum, or copper-clad aluminum.  More aluminum, more current - the wider the diameter.  
   * [100 Amp Service uses 1/0 AWG](https://community.openenergymonitor.org/t/ct-hole-diameter-for-north-america/5149/3) = [12.08 mm](https://lugsdirect.com/Wire_Insulation_Outside_Diameter_Thickness_600V.html).  
   * 200 Amp Service uses (up to?) 2/0 - 4/0 AWG.  [4/0 AWG has an Outside diameter of 16.04mm](https://lugsdirect.com/Wire_Insulation_Outside_Diameter_Thickness_600V.html).  
* Whether the burden resistor is included.  This design assumes the CT __does not__ include the burden resistor.  I.e.: it's output is a current and not a voltage.  
* The ratio of I(in) : I(out)  
* The inclusion of a zener diode.  This is a terrific safety measure to make sure when the CT is clamped on, the circuit is not open.    
# Our Choice of Current Transformers 
 Two Current Transformers (CTs) are needed to get current readings on the two 120V lines.
 ## 100 Amp   
  We'll be using [the SCT-013-000 CT](/https://learn.openenergymonitor.org/electricity-monitoring/ct-sensors/yhdc-sct-013-000-ct-sensor-report) for 100A homes.  It is popular with DIY home energy monitors.  There are two numbers of interest in the [YHDC SCT-013-000 datasheet](http://statics3.seeedstudio.com/assets/file/bazaar/product/101990029-SCT-013-000-Datasheet.pdf):    
* The diameter of the clamp opening - 13 mm  
* The I(OUT) - 50 mA  
As Robert Wall of [the Open Energy Monitor project](https://openenergymonitor.org/) noted to me _...the manufacturer will tweak the number of secondary turns to give the best accuracy overall.  The ratio of a c.t. is __ALWAYS__ specified as a ratio of two currents, the rated primary current to the corresponding secondary current. So your SCT-013-000 is __100 A : 50 mA__._ 
## 200 Amp
TBD: We'll know what to use as the project progresses. 
