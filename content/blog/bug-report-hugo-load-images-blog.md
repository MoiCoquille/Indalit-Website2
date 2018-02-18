+++
title = "Bug Report - Hugo - Universal Theme - in BLOG Image Loading Intermittent"
date = "2018-02-18T00:00:00+02:00"
tags = ["Configuration", "Web Development"]
categories = ["Bug Report"]
banner = "img/blog/bug-report-hugo-image-loading.png"
alt = "Hugo Universal Theme Bug Report on Images in Blog"
author = "Veronique Robitaille"
+++

### Environment

* [Hugo Static Website Generator](https://gohugo.io/) version v0.36 
* [Hugo Universal Theme](https://github.com/devcows/hugo-universal-theme)
* Hosted on [AWS S3](https://aws.amazon.com/s3/) in http only
* Image size as per examples : 1000 x 750
* .js and .css files have not been modified

### What should be happening

When going on the [BLOG](http://www.indalit.com/blog/) page, a list of most recent blog post will appear one after the other with the associated image on the left.

### What is happening

* When going on the [BLOG](http://www.indalit.com/blog/) page, a list of most recent blog post will appear one after the other with or without the image on the left.  The image loads or doesn't load randomly.  Sometimes they all appear, sometimes only a few or sometimes none.
* After verification the images all load, they are just not all displayed.
* With some tools, you can see that the pixels set to the image are 0.
* All devices, all browsers.
* Dev environment server and AWS S3 hosting both have the same problem.

### Debugging

* Different size images.
* Various modification to CSS.
* When CSS file removed from the running server, the problem goes away.  This would assume a problem with the CSS file.
* Removal of some .js files.

### Online Support

* Theme GIT repository, Issues section has not been answered for the last 3 months
* [Hugo Community](https://discourse.gohugo.io/) discarded the issue and marked it as closed saying it was a .js problem .
* This is the odd part, nobody on the internet has had the same problem!
* Post on [Stackoverflow](https://stackoverflow.com/) didn't attract any capable of resolving the issue.

### Solution (in this case a work around)

* The root cause was not found.  More investigation would be required.
* We suspect root cause has to do with .js.
* A min-height of 196px was added to the custom.css as follows.

```
#blog-listing-medium .post .image {
    margin-bottom: 10px;
    overflow: hidden;
    min-height: 196px;
}
```

### Outcome & Consequences

* No more problem.
* Works on all devices.
* Wonder what will happen if the actual size of the image to display is less than 196px.


