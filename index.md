---
layout: page
background: '/img/bg-index.jpg'
title: FitHome
description: A Personal Trainer for Lowering Electricity Consumption.
notify: true

---
<link rel="stylesheet" href='{{ '/assets/page-style.css' | prepend: site.baseurl | replace: '//', '/' }}'>

# Save Money   
<a href='{{ '/about/#save_money' | prepend: site.baseurl | replace: '//', '/' }}' target="_blank">Save $200/year - or more </a> on your electricity bill with no changes to your lifestyle.  
# Save lives
[If all households in the US saved at least 15%](https://aceee.org/research-report/h1801){:target="_blank"}:  
  * 6 lives would be saved per day.
  * There would be 30,000 fewer asthma episodes.  

# Combat Climate Change  
Using less electricity makes it easier for renewable energy sources to meet our electricity needs.  
<hr>
# The FitHome Experience
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
# The 15% One Month Challenge
<a id="challenge">
* Takes one month for a one time fee of $59.50.
* Electrician installs and uninstalls the monitor.
* App shows you:  
  * How much electricity your are using.  
  * The simplest and most effective activities to lower your electricity use with no change to your lifestyle.  
  * The impact your savings is having on your wallet and your environment.
* The experience makes you mindful of the positive impact you can have.  
<hr>
Please let us inform you when FitHome is ready.  
<form method="POST" action="https://formspree.io/sparky@fithome.life">
  <div class="control-group">
    <div class="form-group floating-label-form-group controls">
      <label>Email Address</label>
      <input type="email" name="email" class="form-control" placeholder="Email Address" id="email" required
        data-validation-required-message="Please enter your email address.">
      <p class="help-block text-danger"></p>
    </div>
  </div>
  <div id="success"></div>
  <div class="form-group">
    <button type="submit" class="btn btn-primary" id="sendMessageButton">Let me know</button>
  </div>
  <input type="text" name="_gotcha" style="display:none" />
</form>
<!-- <button type="submit" class="btn btn-primary mt-2 text-justify-center">Let me know</button> -->


