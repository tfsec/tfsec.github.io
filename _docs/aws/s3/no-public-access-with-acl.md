---
title: S3 Bucket has an ACL defined which allows public access.
shortcode: aws-s3-no-public-access-with-acl
legacy: AWS001
summary: S3 Bucket has an ACL defined which allows public access. 
resources: [aws_s3_bucket] 
permalink: /docs/aws/s3/no-public-access-with-acl/
redirect_from: 
  - /docs/aws/AWS001/
---

### Explanation


S3 bucket permissions should be set to deny public access unless explicitly required.

Granting write access publicly with <code>public-read-write</code> is especially dangerous as you will be billed for any uploaded files.

Additionally, you should not use the <code>authenticated-read</code> canned ACL, as this provides read access to any authenticated AWS user, not just AWS users within your organisation.


### Possible Impact
The contents of the bucket can be accessed publicly

### Suggested Resolution
Apply a more restrictive bucket ACL


### Insecure Example

The following example will fail the aws-s3-no-public-access-with-acl check.

{% highlight terraform %}

resource "aws_s3_bucket" "bad_example" {
	acl = "public-read"
}

{% endhighlight %}



### Secure Example

The following example will pass the aws-s3-no-public-access-with-acl check.

{% highlight terraform %}

resource "aws_s3_bucket" "good_example" {
	acl = "private"
}

{% endhighlight %}



### Related Links


- [https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/s3_bucket](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/s3_bucket){:target="_blank" rel="nofollow noreferrer noopener"}

- [https://aws.amazon.com/premiumsupport/knowledge-center/secure-s3-resources/](https://aws.amazon.com/premiumsupport/knowledge-center/secure-s3-resources/){:target="_blank" rel="nofollow noreferrer noopener"}


