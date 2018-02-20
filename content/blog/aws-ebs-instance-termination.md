+++
title = "Amazon EBS Volumes Delete on Instance Termination"
date = "2018-02-18T21:49:20+02:00"
tags = ["Configuration", "EC2 Instances", "EBS"]
categories = ["AWS", "Did You Know", "Compute", "Storage"]
banner = "img/blog/aws-ebs-delete-termination.png"
alt = "EBS Data Erased on Instance Termination"
author = "Veronique Robitaille"
+++

Did you know that by default [Amazon](https://aws.amazon.com/) EBS root device volumes are automatically deleted when the instance terminates?

This is also the case with ephemeral storage (instance store volumes).  Other non root EBS volumes are not deleted.  You can configure your instance so it doesn't delete the EBS root device volumes with the **DeleteOnTermination** attribute.

You can find more information on this AWS EBS feature at [What happens to an EBS volume when the instance is terminated?](http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/terminating-instances.html).
