---
layout: home
background: '/img/bg-index.jpg'
title: FitHome
description: Trim the Fat from your Electricity Bills.<br><br>Help Combat Climate Change.
subdescription: Take the 15% Challenge.

---
<link rel="stylesheet" href='{{ '/assets/post-entry-style.css' | prepend: site.baseurl | replace: '//', '/' }}'>

# FitHome is a Personal Trainer for lowering your electricity consumption.  
Save around $200 per year - or more - on your electricity bill.<br>    
Contribute to saving lives.  [If all households in the US saved at least 15%](https://aceee.org/research-report/h1801):  
  * 6 lives would be saved per day.
  * There would be 30,000 fewer asthma episodes.    

It's all about <a href="#challenge">the 15% Challenge!</a>
<br>  
<hr>
# FitHome Experience
The FitHome experience includes...

## FitHome App
The app gives you insight into your electricity use.  Guiding you through easy tasks you can do to save electricity.
<br>
<div class="container-fluid">
  <div class="row">
    <!-- bootstrap uses 12 cols.  I want the carousel to be positioned in the middle. -->
    <div class="col-5 offset-1"> 
      {% include app-carousel.html %}
    </div> 
        {% include app_card.html %}
  </div>
</div>
<br>
<hr>
## FitHome Monitor   
The monitor reads the amount of electricity your devices are using and sends this info to your phone.
<br>
<div class="container-fluid">
  <div class="row">
    <!-- bootstrap uses 12 cols.  I want the carousel to be positioned in the middle. -->
    <div class="col-5 offset-1"> 
      {% include monitor-carousel.html %}
    </div> 
        {% include monitor_card.html %}
  </div>
</div>
<br>
<hr>
# 15% One Month Challenge
<a id="challenge">TBD
