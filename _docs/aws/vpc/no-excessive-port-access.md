---
title: aws-vpc-no-excessive-port-access
description: An ingress Network ACL rule allows ALL ports.
shortcode: aws-vpc-no-excessive-port-access
legacy: AWS050
summary: An ingress Network ACL rule allows ALL ports. 
resources: [aws_network_acl_rule] 
permalink: /docs/aws/vpc/no-excessive-port-access/
redirect_from: 
  - /docs/aws/AWS050/
---

### Explanation


Ensure access to specific required ports is allowed, and nothing else.


### Possible Impact
All ports exposed for egressing data

### Suggested Resolution
Set specific allowed ports


### Insecure Example

The following example will fail the aws-vpc-no-excessive-port-access check.

{% highlight terraform %}

resource "aws_network_acl_rule" "bad_example" {
  egress         = false
  protocol       = "all"
  rule_action    = "allow"
  cidr_block     = "0.0.0.0/0"
}

{% endhighlight %}



### Secure Example

The following example will pass the aws-vpc-no-excessive-port-access check.

{% highlight terraform %}

resource "aws_network_acl_rule" "good_example" {
  egress         = false
  protocol       = "tcp"
  from_port      = 22
  to_port        = 22
  rule_action    = "allow"
  cidr_block     = "0.0.0.0/0"
}

{% endhighlight %}



### Related Links


- [https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/network_acl_rule#to_port](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/network_acl_rule#to_port){:target="_blank" rel="nofollow noreferrer noopener"}

- [https://docs.aws.amazon.com/vpc/latest/userguide/vpc-network-acls.html](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-network-acls.html){:target="_blank" rel="nofollow noreferrer noopener"}


