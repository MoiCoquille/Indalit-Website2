+++
title = "Debugging www.indalit.com"
date = "2018-02-18T00:00:20+02:00"
tags = ["Creating My Company"]
categories = ["Diary"]
banner = "img/blog/veronique-wonderwoman.jpg"
alt = "Veronique Wonder Woman Debugging"
author = "Veronique Robitaille"
+++

<p>
On my previous post I was working on <a href="http://www.indalit.com">www.indalit.com</a>.  First of all, I, innocent me, actually thought I was finished.  But then, I made the mistake at looking at the page with my mobile phone!!!  And then making my browser screen smaller!!!  Wow, horrible.  So, it turns out working with CSS and positioning correctly DIVs is just not a beginners thing.  Took me hours of work.  Now it works great, but my associate has decided it needs to be centered.  So, as anyone who has CSS knowledge knows centering DIVs is not the simplest thing.  At this stage I've had enough, so it's all up to him to fix it.  I tried a couple of things without success, it looks fine as it is.  I'm done.
</p>
<p>
Now, I had a second problem, this one was tough.  I spend 2 days on it with little success, it got better, but not completely fixed.  The <a href="http://www.indalit.com/blog/">BLOG</a> page would load images randomly. Sometimes the last 6 wouldn't load, then the first, then they would load, then none, ...  Not the browsers, not the hosting, not the servers,...  In the end, with my knowledge, I had to handover this issue to my associate :-( who obviously managed to fix it since he's a first class geek who fixes anything.  A bit disappointing for me.
</p>
<p>
On the upside, the website is now hosted on <a href="https://aws.amazon.com/s3/" target="_blank">AWS S3</a>.  We chose <a href="https://gohugo.io/" target="_blank">Hugo</a>, a static website generator so we could host our site on Amazon without having to worry about servers and databases.  For extra redundancy and speed, it runs through <a href="https://aws.amazon.com/cloudfront/" target="_blank">AWS CloudFront</a>, a <a href="https://en.wikipedia.org/wiki/Content_delivery_network" target="_blank">Content Delivery Network</a> (CDN) solution.
</p>
<p>
What's next? Still the website.  I have left some DIVs to center and we all know this is not always simple.  The carousel just doesn't look good enough, so a redesign around that, all the content needs to be reviewed and more blog entries need to added.  Also move the site to HTTPS and adding languages, and probably more.
</p>
<p>
This week I was a web developer most of the time.  I did some legal work on the contracts, but that's it.  At this stage, I can't really see the goal, there is so much left to do before we can officially open.  For now I'm keeping the most important for last, how the hell am I going to find customers!?!
</p>
<p>
I really like this process, I like doing everything myself and learning new things.  We could have invested a bit more money to outsource some of the tasks, but where would have been the fun in that?
</p>
<p>
UPDATE : I had to tell you, my packs page has been reviewed by my associate.  It's pretty much a pile of crap, errors all over.  At first that upset me, all that work for nothing since it needs to be redone.  BUT, yes there is a but.  I had nested divs all over, rows, classes, ... and while it was all wrong, I managed to make it work accross all devices :-)  Yeah for me!
</p>
