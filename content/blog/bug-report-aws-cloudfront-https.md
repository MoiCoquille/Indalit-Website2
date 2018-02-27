+++
title = "AWS CloudFront Migration to HTTPS with Errors"
date = "2018-02-22T00:49:20+02:00"
tags = ["Configuration", "S3", "Encryption", "Web Development", "CloudFront"]
categories = ["AWS", "Networking & Content Delivery", "Migration", "Bug Report"]
banner = "img/blog/bug-report-aws-cloudfront-https.png"
alt = "AWS CloudFront Migration to HTTPS ISSUE"
author = "Veronique Robitaille"
+++

I need to start this by saying there is NO bug with <i>AWS CloudFront</i>, NO bug with <i>AWS S3</i>, NO bug with Hugo and NO bug with OWL Carousel javascript.  This is a Veronique bug.  I just wanted to document this in case someone has a similar problem.  I was unable to find the solution on the internet with the search strings I used.

### Environment

* [Hugo Static Website Generator](https://gohugo.io/) version v0.36 
* [Hugo Universal Theme](https://github.com/devcows/hugo-universal-theme)
* Hosted on [AWS S3](https://aws.amazon.com/s3/) in HTTP only
* Website distributed via a <a href="https://en.wikipedia.org/wiki/Content_delivery_network" target="_blank">Content Delivery Network</a> (CDN) solution called <a href="https://aws.amazon.com/cloudfront/" target="_blank">AWS CloudFront</a> in HTTPS
* Use of owl.carouseol.js for the carousel on the homepage

### What should be happening

The homepage of [https://www.indalit.com](https://www.indalit.com/) should display the carouseil which is composed of 3 different slides that move horizontally.

### What is happening

* On <i>AWS CloudFront</i> only, not my development environment and not on <i>AWS S3</i>, the carousel does not work.  All three slides are displayed one after the other.
* There was another part on the homepage that didn't work, but I wasn't looking into that at that time.
* All devices, all browsers.

### Debugging

* I tried comparing some files like index.html to see if the versions where the same or if there was any difference between the one on <i>AWS S3</i> and <i>AWS CloudFront</i>
* Search the internet for a similar problem without any luck.
* Inspect the index.html with a browser tool. 

### Online Support

* Posted on <a href="https://github.com/OwlCarousel2/OwlCarousel2/issues/2227"target="_blank">Github OWL Carousel</a>

### Solution

* On GitHub a guy was nice enough to answer me even though my problem had absolutely nothing to do with OWL Carousel.  When I passed my site on <i>AWS CloudFront</i> to HTTPS, I didn't make any modifications to any of my configuration files nor HTML files.  That was the problem.  The homepage was calling HTTP elements and HTTPS elements for which the result was the JAVASCRIPT didn't work.  So what you need to do is if you have a configuration file with a base URL, you need to change the HTTP to HTTPS.  If you have http://www.yoursite.com in your HTML files then that also needs to be changed.


### Outcome & Consequences

* No more problem.
* Works on all devices.
