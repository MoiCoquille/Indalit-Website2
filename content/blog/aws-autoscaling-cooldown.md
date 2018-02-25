+++
title = "AWS Auto Scaling Cooldown Period"
date = "2017-06-13T21:49:20+02:00"
tags = ["Auto Scaling", "Configuration"]
categories = ["AWS", "Did You Know?", "Compute"]
banner = "img/blog/aws-autoscaling-cooldown.jpg"
alt = "Cooldown Period in Auto Scaling"
author = "Veronique Robitaille"
dyn_more = """
If you are curious about this feature, then go read more information on <a href="https://docs.aws.amazon.com/autoscaling/ec2/userguide/Cooldown.html" target="_blank">Amazon Aurora Cooldown Period</a>.
"""
+++

Did you know the default AWS Auto Scaling cooldown period is 300 seconds?  When AWS Auto Scaling launches a new instance, it will wait 300 seconds before launching a new one.
