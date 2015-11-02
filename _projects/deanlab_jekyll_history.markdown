---
title: "The Dean Lab Website History"
date:   2015-10-29 09:53:14
categories: jekyll
---

We originally had built a simple node.js based CMS for managing the website for The Dean Lab, a nanoelectronics laboratory out of Columbia University.  This was to hold research, news equipment, and other information related to the interesting doings at The Dean Lab. 

The original CMS was a node.js based application using express.  MongoLabs was used to host the MongoDB backend.  Jade was used for templating.  Cloudinary was used to host the images.  Heroku was used to host the application itself.

This all worked very nicely for a good number of years.  The number of pages stayed fairly small - we had expected the page count to grow quite rapidly, but this never materialized. 

Eventually, MongoLabs upgraded their MongoDB version to 3.x, and this broke the site.  They gave plenty of warning, but we were asleep at the switch.  Easy enough to make a couple of changes to get it running again, but got us thinking - with the number and types of pages in this site, static pages might just make more sense - plus we wouldn't need to worry about issues maintaining an application server and a database server.


[DeanLab]: http://deanlab.github.io
