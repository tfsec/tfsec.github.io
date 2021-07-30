---
title: EBS volumes must be encrypted
shortcode: aws-ebs-enable-volume-encryption
legacy: 
summary: EBS volumes must be encrypted 
resources: [aws_ebs_volume] 
permalink: /docs/aws/ebs/enable-volume-encryption/
redirect_from: 
  - /docs/aws//
---

### Explanation

By enabling encryption on EBS volumes you protect the volume, the disk I/O and any derived snapshots from compromise if intercepted.

### Possible Impact
Unencrypted sensitive data is vulnerable to compromise.

### Suggested Resolution
Enable encryption of EBS volumes


### Insecure Example

The following example will fail the aws-ebs-enable-volume-encryption check.

{% highlight terraform %}

resource "aws_ebs_volume" "bad_example" {
  availability_zone = "us-west-2a"
  size              = 40

  tags = {
    Name = "HelloWorld"
  }
  encrypted = false
}

{% endhighlight %}



### Secure Example

The following example will pass the aws-ebs-enable-volume-encryption check.

{% highlight terraform %}

resource "aws_ebs_volume" "good_example" {
  availability_zone = "us-west-2a"
  size              = 40

  tags = {
    Name = "HelloWorld"
  }
  encrypted = true
}

{% endhighlight %}



### Related Links


- [https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/ebs_volume#encrypted](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/ebs_volume#encrypted){:target="_blank" rel="nofollow noreferrer noopener"}


