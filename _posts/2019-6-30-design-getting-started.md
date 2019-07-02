---
layout: post
title: ""
description: "Design - The Experience from Getting an Email to Monitoring Energy"
background: '/img/bg-post.jpg'
---
<link rel="stylesheet" href='{{ '/assets/post-entry-style.css' | prepend: site.baseurl | replace: '//', '/' }}'>  
  
# Design - Getting Started
A homeowner finds out about FitHome from a post on NextDoor.  The post includes an email address to get started.
![sketch image of getting started](/assets/post-imgs/post-2019-6-30/contact_through_monitoring.png)

# 1
The homeowner either mails or sends a text to us.  We email/text back:  
  
1) a "contract" to sign that states the homeowner will commit to one month of FitHome Personal Electricity Savings Training.  
2) a request for additional information, explaining why we need it:  

* email address (used to create a membership)
* home address (needed by the electrician to install the monitor)   
* contact phone/text number (needed to exchange info from us to the member)  
  
3) letting them know an electrician will be contacting them to install the energy monitor.  
# 2
We:  
* Assign an energy monitor to the homeowner.  
* Make a pre-member entry into the Firebase RT db.    

![pre-member entry](/assets/post-imgs/post-2019-6-30/pre-members-db.png)  

* Contact the electrictian.  We give the electrician the homeowner's address, contact info, and energy monitor.
* We contact the homeowner to let them know an electrician will be contacting them.  
  
# 3 
The electrician:  
* Contacts the homeowner and arranges a date/time for an in-home visit to install the energy monitor in the homeowner's circuit panel.  
* Installs the energy monitor.  
* Works with the homeowner to connect the energy monitor to the home's wifi.

Once the energy monitor is installed and connected to the home's wifi, it starts sending power readings to the Firebase RT db. One weeks worth of readings are taken prior to the start of the FitHome member's 3 week personal training session.    
  
# 4
The homeowner:  
* (4.1) Installs and launches the FitHome app on their smartphone.
* (4.2) Creates a Member account by entering their email and a password.  _Note: The email must be the same email given to us earlier._ 
* (4.3) Verifies the homeowner is getting data on their app by viewing the impact screen.  

During this time, the app shows the Impact Screen.  However, the Analysis and Leaderboard screen aren't available.  They show a countdown of how much time is left before their FitHome session begins.   By starting with a week's worth of data, we can personalize electricity savings advice based on how they currently use electricity.


  


