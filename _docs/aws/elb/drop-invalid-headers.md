---
title: aws-elb-drop-invalid-headers
description: Load balancers should drop invalid headers
shortcode: aws-elb-drop-invalid-headers
legacy: AWS083
summary: Load balancers should drop invalid headers 
resources: [aws_alb aws_lb] 
permalink: /docs/aws/elb/drop-invalid-headers/
redirect_from: 
  - /docs/aws/AWS083/
---

### Explanation


Passing unknown or invalid headers through to the target poses a potential risk of compromise. 

By setting drop_invalid_header_fields to true, anything that doe not conform to well known, defined headers will be removed by the load balancer.


### Possible Impact
Invalid headers being passed through to the target of the load balance may exploit vulnerabilities

### Suggested Resolution
Set drop_invalid_header_fields to true


### Insecure Example

The following example will fail the aws-elb-drop-invalid-headers check.

{% highlight terraform %}

resource "aws_alb" "bad_example" {
	name               = "bad_alb"
	internal           = false
	load_balancer_type = "application"
	
	access_logs {
	  bucket  = aws_s3_bucket.lb_logs.bucket
	  prefix  = "test-lb"
	  enabled = true
	}
  
	drop_invalid_header_fields = false
  }

{% endhighlight %}



### Secure Example

The following example will pass the aws-elb-drop-invalid-headers check.

{% highlight terraform %}

resource "aws_alb" "good_example" {
	name               = "good_alb"
	internal           = false
	load_balancer_type = "application"
	
	access_logs {
	  bucket  = aws_s3_bucket.lb_logs.bucket
	  prefix  = "test-lb"
	  enabled = true
	}
  
	drop_invalid_header_fields = true
  }

{% endhighlight %}



### Related Links


- [https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/lb#drop_invalid_header_fields](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/lb#drop_invalid_header_fields){:target="_blank" rel="nofollow noreferrer noopener"}

- [https://docs.aws.amazon.com/elasticloadbalancing/latest/application/application-load-balancers.html](https://docs.aws.amazon.com/elasticloadbalancing/latest/application/application-load-balancers.html){:target="_blank" rel="nofollow noreferrer noopener"}


