---
title: ECR images tags shouldn't be mutable.
shortcode: aws-ecr-enforce-immutable-repository
legacy: AWS078
summary: ECR images tags shouldn't be mutable. 
resources: [aws_ecr_repository] 
permalink: /docs/aws/ecr/enforce-immutable-repository/
redirect_from: 
  - /docs/aws/AWS078/
---

### Explanation


ECR images should be set to IMMUTABLE to prevent code injection through image mutation.

This can be done by setting <code>image_tab_mutability</code> to <code>IMMUTABLE</code>


### Possible Impact
Image tags could be overwritten with compromised images

### Suggested Resolution
Only use immutable images in ECR


### Insecure Example

The following example will fail the aws-ecr-enforce-immutable-repository check.

{% highlight terraform %}

resource "aws_ecr_repository" "bad_example" {
  name                 = "bar"
  image_tag_mutability = "MUTABLE"

  image_scanning_configuration {
    scan_on_push = true
  }
}

{% endhighlight %}



### Secure Example

The following example will pass the aws-ecr-enforce-immutable-repository check.

{% highlight terraform %}

resource "aws_ecr_repository" "good_example" {
  name                 = "bar"
  image_tag_mutability = "IMMUTABLE"

  image_scanning_configuration {
    scan_on_push = true
  }
}

{% endhighlight %}



### Related Links


- [https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/ecr_repository](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/ecr_repository){:target="_blank" rel="nofollow noreferrer noopener"}

- [https://sysdig.com/blog/toctou-tag-mutability/](https://sysdig.com/blog/toctou-tag-mutability/){:target="_blank" rel="nofollow noreferrer noopener"}


