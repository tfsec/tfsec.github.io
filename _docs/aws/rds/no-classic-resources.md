---
title: AWS Classic resource usage.
shortcode: aws-rds-no-classic-resources
legacy: AWS003
summary: AWS Classic resource usage. 
resources: [aws_db_security_group aws_redshift_security_group aws_elasticache_security_group] 
permalink: /docs/aws/rds/no-classic-resources/
redirect_from: 
  - /docs/aws/AWS003/
---

### Explanation


AWS Classic resources run in a shared environment with infrastructure owned by other AWS customers. You should run
resources in a VPC instead.


### Possible Impact
Classic resources are running in a shared environment with other customers

### Suggested Resolution
Switch to VPC resources


### Insecure Example

The following example will fail the aws-rds-no-classic-resources check.

{% highlight terraform %}

resource "aws_db_security_group" "bad_example" {
  # ...
}

{% endhighlight %}



### Secure Example

The following example will pass the aws-rds-no-classic-resources check.

{% highlight terraform %}

resource "aws_security_group" "good_example" {
  # ...
}

{% endhighlight %}



### Related Links


- [https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/db_security_group](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/db_security_group){:target="_blank" rel="nofollow noreferrer noopener"}

- [https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-classic-platform.html](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-classic-platform.html){:target="_blank" rel="nofollow noreferrer noopener"}


