+++
title = "AWS EC2 Intances Metadata"
date = "2017-06-17T21:49:20+02:00"
tags = ["Configuration", "EC2 Instances", "IP", "OS"]
categories = ["AWS", "Did You Know", "Compute"]
banner = "img/blog/aws-ec2-instances-metadata.jpg"
alt = "Text"
author = "Veronique Robitaille"
dyn_more = """
For more information on AWS EC2 Instances see: <a href="http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-instance-metadata.html" target="_blank">Amazon EC2 Instance Metadata</a>.
"""
+++
Did you know that viewing the following link on an AWS EC2 instance will give you the metadata of your instance? 

```
http://169.254.169.254/latest/meta-data/
```
