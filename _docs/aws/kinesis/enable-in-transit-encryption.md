---
title: Kinesis stream is unencrypted.
shortcode: aws-kinesis-enable-in-transit-encryption
legacy: AWS024
summary: Kinesis stream is unencrypted. 
resources: [aws_kinesis_stream] 
permalink: /docs/aws/kinesis/enable-in-transit-encryption/
redirect_from: 
  - /docs/aws/AWS024/
---

### Explanation


Kinesis streams should be encrypted to ensure sensitive data is kept private. Additionally, non-default KMS keys should be used so granularity of access control can be ensured.


### Possible Impact
Intercepted data can be read in transit

### Suggested Resolution
Enable in transit encryption


### Insecure Example

The following example will fail the aws-kinesis-enable-in-transit-encryption check.

{% highlight terraform %}

resource "aws_kinesis_stream" "bad_example" {
	encryption_type = "NONE"
}

{% endhighlight %}



### Secure Example

The following example will pass the aws-kinesis-enable-in-transit-encryption check.

{% highlight terraform %}

resource "aws_kinesis_stream" "good_example" {
	encryption_type = "KMS"
	kms_key_id = "my/special/key"
}

{% endhighlight %}



### Related Links


- [https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/kinesis_stream#encryption_type](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/kinesis_stream#encryption_type){:target="_blank" rel="nofollow noreferrer noopener"}

- [https://docs.aws.amazon.com/streams/latest/dev/server-side-encryption.html](https://docs.aws.amazon.com/streams/latest/dev/server-side-encryption.html){:target="_blank" rel="nofollow noreferrer noopener"}


