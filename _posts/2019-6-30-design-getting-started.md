---
layout: post
title: ""
description: "Design - Getting Started"
background: '/img/bg-post.jpg'
---
<link rel="stylesheet" href='{{ '/assets/post-entry-style.css' | prepend: site.baseurl | replace: '//', '/' }}'>  
  
This post describes the process of becoming a Fithome member and starting to send the first readings.  

The goal is to put a process in code that:  
* is accountable by tracking the steps and ensuring each one has been completed within a "time commitment promise" we want to make.   
* minimizes the possibility of homeowner frustration by providing UI and process that are clear, actionable, and easy to follow.

The process starts with downloading the Fithome app.

# (1) Download FitHome App
A homeowner downloads the FitHome app from either the Apple App Store or Google Play store.
![sketch image of getting started](/assets/post-imgs/post-2019-6-30/contact_through_monitoring.png)

# (2) Become a Member
The app checks the available_monitors node of the Firebase db to see if there are monitors available.   
![available monitors](/assets/post-imgs/post-2019-6-30/firebase_available_monitors.png).  

(2A) If there are monitors available, the homeowner is shown the Start Training screen.  
![Start training screen](/assets/post-imgs/post-2019-6-30/start_training_screen.png).  
(2B) If there is a waitlist, the homeowner is shown the waiting list sign up screen.  
![Waitlist screen](/assets/post-imgs/post-2019-6-30/waitlist_screen.png)

## Geographic Location
Whichever screen is shown, the homeowner is made aware of the limited geographic availability of the FitHome experience.  The limit is to make sure the homeowner will have a quality experience since personalized interactions are part of the experience.  For example, when an electrician comes out to install the monitor.
### Supported Zip Codes
The FitHome experience ends here for a homeowner that does not find their zip code listed.  At this point, the homeowner can delete the FitHome app.  
  
If their zip code is listed, they continue with the following....
## (2A) Start Training
The homeowner enters member registration information and then taps on the "START TRAINING".
### Create Account
After tapping "START TRAINING", the app uses the email and password to create an account in the Firebase account database.   
![Firebase account](/assets/post-imgs/post-2019-6-30/firebase_account_console_view.png)
### Store Member Info
 Next, the app creates a node in the Firebase db where the node name is the user id.  The node contains additional fields collected on the Start Training screen.
 ![Firebase member entry](/assets/post-imgs/post-2019-6-30/firebase_db_member_entry.png)  

The app removes one of the monitor names from the available_monitors node, appends the month/date/year, and stores this as the machine within the Member Info node.  For example, if the date was 07/05/2019 and the available monitor was named bambi, the entry would be bambi-07052019.

Other fields created by the app include: 
* start_timestamp - This field is set when the homeowner taps the START TRAINING button.  
* install_timestamp - This field is set when the homeowner taps on the SCHEDULE ELECTRICIAN button.  
* active_timestamp - This field is set by the monitor when it first starts taking readings.
* wait_timestamp - This field exists if the homeowner is (or has been) on the waiting list.  The number of homeowners on the waiting list are the number of Member Entries that have the wait_timestamp filled and do not have their start_timestamp filled.
* done_timestamp - This field is filled when the FitHome experience ends.   
  
The status field can be either:  
* start - The homeowner tapped the START TRAINING button.  
* install - The homeowner tapped the SCHEDULE ELECTRICIAN button.
* baseline - The monitor has been installed, however baseline info is not ready yet.  
* active - The FitHome personal training experience is ongoing.  
* wait - This Member is on the waiting list.  
* done - The FitHome experience has completed.   
  
These fields are created as the state of the experience changes.  They will be used for FitHome member services to track the installation and active progress of the homeowner.  This way, we will ensure a positive and efficient process experience.

 #### Firebase Event - Monitor Handling
A Firebase function is triggered when a Firebase member entry is created.  The Firebase function sends a text message to FitHome member services.  The text message includes the machine name of the monitor assigned to the homeowner.  When FitHome member services receives the text message, they:  
* Get a monitor from inventory.  
* Label the machine with the machine name.  
* Add the machine name and Firebase RT database project ID to the config.json file as described in [this writeup](https://github.com/BitKnitting/energy_monitor_firmware#configjson).
### (4) Setting up Monitor Installation Appointment
The homeowner sets up a 1/2 hour appointment for an electrician to come out and install the monitor.  
![monitor installation screen](/assets/post-imgs/post-2019-6-30/monitor_installation_screen.png)  

The available dates/times are pulled from the available_times node. ![available time node](/assets/post-imgs/post-2019-6-30/firebase_available_times.png)

The available_time field of the member info node is set to the number of the available_time used.  This way, we can track what appointment has been set for this member.

#### Firebase Event - Electrician Assignment
A Firebase function sends an SMS to the electrician noted in the available_time assigned to the member.  The installation is scheduled.
### (5) Monitor Installation
After plugging the CTs into the energy monitor, the electrician installs the CTs on the two power lines.  The energy monitor is either plugged into an available socket, or the circuit breaker socket is used to add a plug from the circuit breaker box.
### (6) Connecting to wifi
The homeowner uses their laptop to connect the monitor to their home wifi as discussed [in this writeup](https://github.com/BitKnitting/energy_monitor_firmware#join-the-homeowners-wifi)
### (7) Start Sending Readings 
Now that the monitor is connected to the wifi and the CTs have been installed, it will start sending power readings to the db.







