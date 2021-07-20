---
title: aws-rds-encrypt-instance-storage-data - RDS encryption has not been enabled at a DB Instance level.
summary: RDS encryption has not been enabled at a DB Instance level. 
resources: [aws_db_instance] 
permalink: /docs/aws/aws-rds-encrypt-instance-storage-data/
---
### Explanation


Encryption should be enabled for an RDS Database instances. 

When enabling encryption by setting the kms_key_id. 


### Possible Impact
Data can be read from RDS instances if compromised

### Suggested Resolution
Enable encryption for RDS instances


### Insecure Example

The following example will fail the aws-rds-encrypt-instance-storage-data check.

{% highlight terraform %}

resource "aws_db_instance" "bad_example" {
	
}

{% endhighlight %}



### Secure Example

The following example will pass the aws-rds-encrypt-instance-storage-data check.

{% highlight terraform %}

resource "aws_db_instance" "good_example" {
	storage_encrypted  = true
}

{% endhighlight %}



### Related Links


- [https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/db_instance](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/db_instance){:target="_blank" rel="nofollow noreferrer noopener"}

- [https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Overview.Encryption.html](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Overview.Encryption.html){:target="_blank" rel="nofollow noreferrer noopener"}


