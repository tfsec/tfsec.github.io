---
title: aws-s3-block-public-acls - S3 Access block should block public ACL
summary: S3 Access block should block public ACL 
resources: [aws_s3_bucket_public_access_block] 
permalink: /docs/aws/aws-s3-block-public-acls/
---
### Explanation


S3 buckets should block public ACLs on buckets and any objects they contain. By blocking, PUTs with fail if the object has any public ACL a.


### Possible Impact
PUT calls with public ACLs specified can make objects public

### Suggested Resolution
Enable blocking any PUT calls with a public ACL specified


### Insecure Example

The following example will fail the aws-s3-block-public-acls check.

{% highlight terraform %}

resource "aws_s3_bucket_public_access_block" "bad_example" {
	bucket = aws_s3_bucket.example.id
}

resource "aws_s3_bucket_public_access_block" "bad_example" {
	bucket = aws_s3_bucket.example.id
  
	block_public_acls = false
}

{% endhighlight %}



### Secure Example

The following example will pass the aws-s3-block-public-acls check.

{% highlight terraform %}

resource "aws_s3_bucket_public_access_block" "good_example" {
	bucket = aws_s3_bucket.example.id
  
	block_public_acls = true
}

{% endhighlight %}



### Related Links


- [https://docs.aws.amazon.com/AmazonS3/latest/userguide/access-control-block-public-access.html](https://docs.aws.amazon.com/AmazonS3/latest/userguide/access-control-block-public-access.html){:target="_blank" rel="nofollow noreferrer noopener"}

- [https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/s3_bucket_public_access_block#block_public_acls](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/s3_bucket_public_access_block#block_public_acls){:target="_blank" rel="nofollow noreferrer noopener"}


