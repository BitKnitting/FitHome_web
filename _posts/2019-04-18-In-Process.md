---
layout: post
title: "Easy to make a web site"
subtitle: "with GitHub pages"
background: '/img/bg-post.jpg'
---
I used GitHub pages to create the [FitHome web site](https://bitknitting.github.io/FitHome_web/).  
GitHub has a nifty way to build a website that uses Jekyll. I'm new to Jekyll.  So far there is alot to like:
* I can write pages in markdown.
* It is heavily template based - this reminds me alot like Flask.
* A web site can start off with a basic template.
* A local web site can run that automagically updates when changes are made to the file (like Flask).  
  
_Note: I have already installed a local copy of Jekyll._
#### Steps
I decided to start with [the clean blog template from Start Bootstrap](https://startbootstrap.com/themes/clean-blog-jekyll/).  The tree and template structure is already Jekyll aware.  It uses Bootstrap to make styling the site easier.  It has a look I like.
* Copied to my local repo directory.  
* Changed the base URL from "/startbootstrap-clean-blog-jekyll" to "".  
* Changed th url from " "http://blackrockdigital.github.io" to "http://bitknitting.github.io"
* Made sure it worked on Localhost:4000.  ```bundle exec jekyll serve```
* Deleted the original .git directory (I found deleting Start Bootstrap's repo the easiest way to link to my remote repo)
* Created a git repository: ```git init``` 
* Created a gh_pages branch.  ```git checkout -b gh-pages``` _Note: The github pages doc says the website can be created under master.  I had a heckuva time with this so I fell back to blindly following steps from YouTube videos, [like this one, Hosting on GitHub](https://www.youtube.com/watch?v=fqFjuX4VZmU)_.  
* Push local git to gitHub ```
* ```git add .```
* ```git commit -m 'first commit'```
* ```git remote add origin https://github.com/BitKnitting/Material_Design_Lite.git```
* ```git push -u origin gh-pages```  
* __TBD__ _Didn't have to do this the second time I tried_ Modify baseurl in _config.yml to be name of GitHub repo.
* Created a new repository - [FitHome_web]() without a Readme.md.   
* Went into Settings/Branches and set ```gh-pages``` as the default branch.  I did this to make sure I always went to this branch.  
* Turn on pages in Settings if not already on.  Make sure to use ```gh-pages``` branch.

 