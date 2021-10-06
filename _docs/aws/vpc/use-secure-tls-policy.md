---
title: An outdated SSL policy is in use by a load balancer.
shortcode: aws-vpc-use-secure-tls-policy
legacy: AWS010
summary: An outdated SSL policy is in use by a load balancer. 
resources: [aws_lb_listener aws_alb_listener] 
permalink: /docs/aws/vpc/use-secure-tls-policy/
redirect_from: 
  - /docs/aws/AWS010/
---

### Explanation


You should not use outdated/insecure TLS versions for encryption. You should be using TLS v1.2+. 


### Possible Impact
The SSL policy is outdated and has known vulnerabilities

### Suggested Resolution
Use a more recent TLS/SSL policy for the load balancer


### Insecure Example

The following example will fail the aws-vpc-use-secure-tls-policy check.

{% highlight terraform %}

resource "aws_alb_listener" "bad_example" {
	ssl_policy = "ELBSecurityPolicy-TLS-1-1-2017-01"
	protocol = "HTTPS"
}

{% endhighlight %}



### Secure Example

The following example will pass the aws-vpc-use-secure-tls-policy check.

{% highlight terraform %}

resource "aws_alb_listener" "good_example" {
	ssl_policy = "ELBSecurityPolicy-TLS-1-2-2017-01"
	protocol = "HTTPS"
}

{% endhighlight %}



### Related Links


- [https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/lb_listener](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/lb_listener){:target="_blank" rel="nofollow noreferrer noopener"}


