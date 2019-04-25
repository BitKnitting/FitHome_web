---
layout: post
title: ""
description: Getting the URL paths right
background: '/img/bg-post.jpg'
---
<link rel="stylesheet" href='{{ '/assets/post-entry-style.css' | prepend: site.baseurl | replace: '//', '/' }}'>
Wow.  Jekyll + GitHub pages + Bootstrap 4 (and maybe material design...not sure yet!) is a powerful combo.  The biggest challenge I have had is getting links working when running a local copy AND github pages.
# The Challenge
The challenge with getting links right include:  
* Beginning knowledge to the intricate world of absolute/relative and perhaps other paths.  
* Unique characteristics of how Jekyll / GitHub pages interact.
## The BaseURL
The AHA! Light turned on for me after reading [Parker's article "_Clearing Up Confusion Around baseurl--Again_"](https://byparker.com/blog/2014/clearing-up-confusion-around-baseurl/)
I used GitHub pages to create the [FitHome web site](https://bitknitting.github.io/FitHome_web/).  

As Parker points out: _TL;DR: Use baseurl when you are building a site that doesn’t sit at the root of the domain._

so I put this in _config.yml: ```baseurl: /FitHome_web```
where FitHome_web is the GitHub project for the website.  
The local server (set up after running ```bundle exec jekyll serve```) is found at ```localhost:4000/FitHome_web/```  

  __DO NOT FORGET THE TRAILING SLASH__ as I kept doing...sadly...
## Building The Link  
[head.html](_includes/head.html) shows a line that tells the web site both locally and on the https://bitknitting.github.io/FitHome_web/ servier where the main.css file is located.  

```  <link rel="stylesheet" href='{{ '/assets/main.css' | prepend: site.baseurl | replace: '//', '/' }}'>```  

Now - this is new to me but seems very cool - Jekyll implements _Liquid Filters_.  I like to know where this stuff comes from and found [shopify started all this and then open sourced](https://help.shopify.com/en/themes/liquid).  Info for the two Liquid Filters used above can be found in [Jekyll's documenation](https://jekyllrb.com/docs/liquid/filters/). The href resolves to ```/FitHome_web/assets/main.css```.  If there was a ```//```, this would be replaced with a ```/```.  
[navbar.html](_includes/navbar.html) also makes use of Jekyll's implementation of Liquid Filters to create a url:  

```href='{{ '/tech' | prepend: site.baseurl | replace: '//', '/' }}'```

