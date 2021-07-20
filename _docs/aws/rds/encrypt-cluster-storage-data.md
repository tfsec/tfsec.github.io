---
title: aws-rds-encrypt-cluster-storage-data - There is no encryption specified or encryption is disabled on the RDS Cluster.
summary: There is no encryption specified or encryption is disabled on the RDS Cluster. 
resources: [aws_rds_cluster] 
permalink: /docs/aws/aws-rds-encrypt-cluster-storage-data/
---
### Explanation


Encryption should be enabled for an RDS Aurora cluster. 

When enabling encryption by setting the kms_key_id, the storage_encrypted must also be set to true. 


### Possible Impact
Data can be read from the RDS cluster if it is compromised

### Suggested Resolution
Enable encryption for RDS clusters


### Insecure Example

The following example will fail the aws-rds-encrypt-cluster-storage-data check.

{% highlight terraform %}

resource "aws_rds_cluster" "bad_example" {
  name       = "bar"
  kms_key_id = ""
}
{% endhighlight %}



### Secure Example

The following example will pass the aws-rds-encrypt-cluster-storage-data check.

{% highlight terraform %}

resource "aws_rds_cluster" "good_example" {
  name              = "bar"
  kms_key_id  = "arn:aws:kms:us-west-2:111122223333:key/1234abcd-12ab-34cd-56ef-1234567890ab"
  storage_encrypted = true
}
{% endhighlight %}



### Related Links


- [https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Overview.Encryption.html](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Overview.Encryption.html){:target="_blank" rel="nofollow noreferrer noopener"}

- [https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/rds_cluster](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/rds_cluster){:target="_blank" rel="nofollow noreferrer noopener"}


