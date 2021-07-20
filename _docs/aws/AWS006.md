---
title: An ingress security group rule allows traffic from /0.
shortcode: aws-vpc-no-public-ingress-sgr
legacy: AWS006
summary: An ingress security group rule allows traffic from /0. 
resources: [aws_security_group_rule] 
permalink: /docs/aws/vpc/no-public-ingress-sgr/
redirect_from: 
  - /docs/aws/AWS006/
---

### Explanation


Opening up ports to the public internet is generally to be avoided. You should restrict access to IP addresses or ranges that explicitly require it where possible.


### Possible Impact
Your port exposed to the internet

### Suggested Resolution
Set a more restrictive cidr range


### Insecure Example

The following example will fail the aws-vpc-no-public-ingress-sgr check.

{% highlight terraform %}

resource "aws_security_group_rule" "bad_example" {
	type = "ingress"
	cidr_blocks = ["0.0.0.0/0"]
}

{% endhighlight %}



### Secure Example

The following example will pass the aws-vpc-no-public-ingress-sgr check.

{% highlight terraform %}

resource "aws_security_group_rule" "good_example" {
	type = "ingress"
	cidr_blocks = ["10.0.0.0/16"]
}

{% endhighlight %}



### Related Links


- [https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/security-group-rules-reference.html](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/security-group-rules-reference.html){:target="_blank" rel="nofollow noreferrer noopener"}


