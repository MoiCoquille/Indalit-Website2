+++
title = "How To Make A Template for BLOG Posts"
date = "2018-02-25T00:00:00+02:00"
tags = ["Web Development"]
categories = ["How To"]
banner = "img/blog/how-to.jpg"
alt = "Hugo BLOG Template How To"
author = "Veronique Robitaille"
+++

### How Does It Work Now?

When you create a BLOG post, you can use a template file you have created with all the possible TAGS and CATEGORIES (for example), there might be a better way to handle this with Hugo, but I haven't even looked.  This post is not about creating a template for all BLOG posts, but only for a certain type of BLOG posts.  If you want a specific HTML formatting for only specific types of BLOG posts, then you need to add it to your template file.  This means if you want to modify it, then you go through each BLOG post manually.

### What Do I Want?

I want to use my usual template file to create a new post, but if the BLOG post is a "Did You Know", which I have alot of, then I want a specific HTML layout for those pages.  The reason I want this is because the "Did You Know" BLOG posts are very short and the page is nearly empty, not very esthetic.  But I don't want to have to modify all my "Did You Know" BLOG posts everytime I want to make a change to the HTML layout.

For the HTML, I want two divs with variable data found in the BLOG post .md file.  Here is a screenshot of the page layout I want:

![Screenshot of Layout Requirements](/img/blog/how-to-screenshot-layout.png)

### Is It Possible?

Yes.  With Hugo you have access to all the HTML layouts and can thus modify the one which displays the BLOG posts and create new ones.

### How Do You Do It?

1) Create a new parameter in the BLOG post.  In this case it is dyn_more:


```
title = "AWS Aurora Multi Master Multi AZ"
date = "2018-02-21T21:49:20+02:00"
tags = ["Configuration", "Aurora", "Redundancy", "EC2 Instances", "Availability 
Zone"]
categories = ["AWS", "Did You Know", "Database"]
banner = "img/blog/aws-aurora-multi-master.png"
alt = "AWS Aurora with Multiple Masters in Multiple AZs"
author = "Veronique Robitaille"
dyn_more = """
If you are curious about this feature, then go read more information on <a href=
"https://aws.amazon.com/about-aws/whats-new/2017/11/sign-up-for-the-preview-of-a
mazon-aurora-multi-master/" target="_blank">Amazon Aurora Multi Master</a>.     
      
"""
```


When the .html page is generated, just before it will check if there is a dyn_more parameter in the BLOG post .md file.  If not, then it does as usual and generates the .html page, if there is a dyn_more parameter then it uses the new HTML layout I'm just about to show you.

<br />

2) Create a new layout in /layouts/partials/didyouknow.html as with the following data:

```
<!-- did you know -->
<div class="bkg-texture">
    <div class="dyn-text">
        Did You Know <img class="packimg02" style="float: center" src="/img/blog/interrogation-point.png" alt="Did you know this?">
    </div>
    <div class="dyn-statement">
        {{ .Content }}
    </div>
    <div class="dyn-text">
        Want more information <img class="packimg02" style="float: center" src="/img/blog/interrogation-point.png" alt="Did you know this?">
    </div>
    <div class="dyn-statement">
        {{ .Params.dyn_more | safeHTML }}
    </div>
</div>
```

This will generate a specific HTML layout for my "Did You Know" BLOG posts.

<br />

3) In /layouts/_default/single.html, the following was added:

```
<div id="post-content">
	{{ if .Params.dyn_more }}
		{{ partial "didyouknow.html" . }}
	{{ else }}
		{{ .Content }}
	{{ end }}
</div>
```

<br />

To replace:

```
{{ .Content }}
```

<br />

### What Does It Do Now?

The content part of my BLOG post .md file is inserted in the first rectangle on the screenshot I added above.  The parameter content from dyn_more is added to the second rectangle on the screenshot I added above.

You can have HTML in both of the rectangles, safeHTML was used for the data contained in dyn_more.

I added the dyn_more parameter to the file I copy (template) to my new BLOG posts which has everything that can be filled out and the list of all TAGS and CATEGORIES.
