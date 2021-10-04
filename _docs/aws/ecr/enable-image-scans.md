---
title: aws-ecr-enable-image-scans
description: ECR repository has image scans disabled.
shortcode: aws-ecr-enable-image-scans
legacy: AWS023
summary: ECR repository has image scans disabled. 
resources: [aws_ecr_repository] 
permalink: /docs/aws/ecr/enable-image-scans/
redirect_from: 
  - /docs/aws/AWS023/
---

### Explanation


Repository image scans should be enabled to ensure vulnerable software can be discovered and remediated as soon as possible.


### Possible Impact
The ability to scan images is not being used and vulnerabilities will not be highlighted

### Suggested Resolution
Enable ECR image scanning


### Insecure Example

The following example will fail the aws-ecr-enable-image-scans check.

{% highlight terraform %}

resource "aws_ecr_repository" "bad_example" {
  name                 = "bar"
  image_tag_mutability = "MUTABLE"

  image_scanning_configuration {
    scan_on_push = false
  }
}

{% endhighlight %}



### Secure Example

The following example will pass the aws-ecr-enable-image-scans check.

{% highlight terraform %}

resource "aws_ecr_repository" "good_example" {
  name                 = "bar"
  image_tag_mutability = "MUTABLE"

  image_scanning_configuration {
    scan_on_push = true
  }
}

{% endhighlight %}



### Related Links


- [https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/ecr_repository#image_scanning_configuration](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/ecr_repository#image_scanning_configuration){:target="_blank" rel="nofollow noreferrer noopener"}

- [https://docs.aws.amazon.com/AmazonECR/latest/userguide/image-scanning.html](https://docs.aws.amazon.com/AmazonECR/latest/userguide/image-scanning.html){:target="_blank" rel="nofollow noreferrer noopener"}


