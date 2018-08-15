+++
title = "AWS Auto Scaling Termination Policy"
date = "2017-06-13T21:49:20+02:00"
tags = ["Configuration", "Auto Scaling"]
categories = ["AWS", "Did You Know?", "Compute"]
banner = "img/blog/aws-autoscaling-termination-policy.png"
alt = "Turning off AWS Auto Scaling"
author = "Veronique Robitaille"
dyn_more = """
If you are curious about this feature, then go read more information on <a href="https://docs.aws.amazon.com/autoscaling/ec2/userguide/as-instance-termination.html#default-termination-policy" target="_blank">AWS Auto Scaling Termination Policy</a>.           
"""
+++
Did you know when you use the default termination policy with <i>AWS Auto Scaling</i> it doesn’t terminate the instance with the oldest launch configuration automatically?  It first tries to balance the number of instances across <i>Availability Zones</i>, then picks the <i>Availability Zone</i> with the most instances and terminates the instance with the oldest launch configuration.  If there are more than one, then it ends the process by randomly picking the instance to terminate.
