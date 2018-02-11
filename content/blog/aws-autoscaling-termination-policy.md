+++
title = "AWS Auto Scaling Termination Policy"
date = "2017-06-13T21:49:20+02:00"
tags = ["Configuration", "Auto Scaling"]
categories = ["AWS", "Did You Know?", "Compute"]
banner = "img/blog/aws-autoscaling-termination-policy.png"
alt = "Turning off AWS Auto Scaling"
author = "Veronique Robitaille"
+++
Did you know when you use the default termination policy with AWS Auto Scaling it doesn’t terminate the instance with the oldest launch configuration automatically?  It first tries to balance the number of instances across Availability Zones, then picks the Availability Zone with the most instances and terminates the instance with the oldest launch configuration.  If there are more than one, then it ends the process by randomly picking the instance to terminate.