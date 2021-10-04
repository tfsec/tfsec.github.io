---
title: aws-elastic-search-encrypt-replication-group
description: Unencrypted Elasticache Replication Group.
shortcode: aws-elastic-search-encrypt-replication-group
legacy: AWS035
summary: Unencrypted Elasticache Replication Group. 
resources: [aws_elasticache_replication_group] 
permalink: /docs/aws/elastic-search/encrypt-replication-group/
redirect_from: 
  - /docs/aws/AWS035/
---

### Explanation


You should ensure your Elasticache data is encrypted at rest to help prevent sensitive information from being read by unauthorised users.


### Possible Impact
Data in the replication group could be readable if compromised

### Suggested Resolution
Enable encryption for replication group


### Insecure Example

The following example will fail the aws-elastic-search-encrypt-replication-group check.

{% highlight terraform %}

resource "aws_elasticache_replication_group" "bad_example" {
        replication_group_id = "foo"
        replication_group_description = "my foo cluster"

        at_rest_encryption_enabled = false
}

{% endhighlight %}



### Secure Example

The following example will pass the aws-elastic-search-encrypt-replication-group check.

{% highlight terraform %}

resource "aws_elasticache_replication_group" "good_example" {
        replication_group_id = "foo"
        replication_group_description = "my foo cluster"

        at_rest_encryption_enabled = true
}

{% endhighlight %}



### Related Links


- [https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/elasticache_replication_group#at_rest_encryption_enabled](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/elasticache_replication_group#at_rest_encryption_enabled){:target="_blank" rel="nofollow noreferrer noopener"}

- [https://docs.aws.amazon.com/AmazonElastiCache/latest/red-ug/at-rest-encryption.html](https://docs.aws.amazon.com/AmazonElastiCache/latest/red-ug/at-rest-encryption.html){:target="_blank" rel="nofollow noreferrer noopener"}


