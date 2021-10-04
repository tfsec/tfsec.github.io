---
title: aws-vpc-no-default-vpc
description: AWS best practice to not use the default VPC for workflows
shortcode: aws-vpc-no-default-vpc
legacy: AWS082
summary: AWS best practice to not use the default VPC for workflows 
resources: [aws_default_vpc] 
permalink: /docs/aws/vpc/no-default-vpc/
redirect_from: 
  - /docs/aws/AWS082/
---

### Explanation


Default VPC does not have a lot of the critical security features that standard VPC comes with, new resources should not be created in the default VPC and it should not be present in the Terraform.


### Possible Impact
The default VPC does not have critical security features applied

### Suggested Resolution
Create a non-default vpc for resources to be created in


### Insecure Example

The following example will fail the aws-vpc-no-default-vpc check.

{% highlight terraform %}

resource "aws_default_vpc" "default" {
	tags = {
	  Name = "Default VPC"
	}
  }

{% endhighlight %}



### Secure Example

The following example will pass the aws-vpc-no-default-vpc check.

{% highlight terraform %}

# no aws default vpc present

{% endhighlight %}



### Related Links


- [https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/default_vpc](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/default_vpc){:target="_blank" rel="nofollow noreferrer noopener"}

- [https://docs.aws.amazon.com/vpc/latest/userguide/default-vpc.html](https://docs.aws.amazon.com/vpc/latest/userguide/default-vpc.html){:target="_blank" rel="nofollow noreferrer noopener"}


