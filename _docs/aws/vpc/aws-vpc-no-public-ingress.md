---
title: aws-vpc-no-public-ingress - An ingress Network ACL rule allows specific ports from /0.
summary: An ingress Network ACL rule allows specific ports from /0. 
resources: [aws_network_acl_rule] 
permalink: /docs/aws/aws-vpc-no-public-ingress/
---
### Explanation


Opening up ACLs to the public internet is potentially dangerous. You should restrict access to IP addresses or ranges that explicitly require it where possible.



### Possible Impact
The ports are exposed for ingressing data to the internet

### Suggested Resolution
Set a more restrictive cidr range


### Insecure Example

The following example will fail the aws-vpc-no-public-ingress check.

{% highlight terraform %}

resource "aws_network_acl_rule" "bad_example" {
  egress         = false
  protocol       = "tcp"
  from_port      = 22
  to_port        = 22
  rule_action    = "allow"
  cidr_block     = "0.0.0.0/0"
}

{% endhighlight %}



### Secure Example

The following example will pass the aws-vpc-no-public-ingress check.

{% highlight terraform %}

resource "aws_network_acl_rule" "good_example" {
  egress         = false
  protocol       = "tcp"
  from_port      = 22
  to_port        = 22
  rule_action    = "allow"
  cidr_block     = "10.0.0.0/16"
}

{% endhighlight %}



### Related Links


- [https://docs.aws.amazon.com/vpc/latest/userguide/vpc-network-acls.html](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-network-acls.html){:target="_blank" rel="nofollow noreferrer noopener"}

