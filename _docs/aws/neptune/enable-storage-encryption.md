---
title: aws-neptune-enable-storage-encryption
description: Neptune storage must be encrypted at rest
shortcode: aws-neptune-enable-storage-encryption
legacy: 
summary: Neptune storage must be encrypted at rest 
resources: [aws_neptune_cluster] 
permalink: /docs/aws/neptune/enable-storage-encryption/
redirect_from: 
  - /docs/aws//
---

### Explanation

Encryption of Neptune storage ensures that if their is compromise of the disks, the data is still protected.

### Possible Impact
Unencrypted sensitive data is vulnerable to compromise.

### Suggested Resolution
Enable encryption of Neptune storage


### Insecure Example

The following example will fail the aws-neptune-enable-storage-encryption check.

{% highlight terraform %}

resource "aws_neptune_cluster" "bad_example" {
  cluster_identifier                  = "neptune-cluster-demo"
  engine                              = "neptune"
  backup_retention_period             = 5
  preferred_backup_window             = "07:00-09:00"
  skip_final_snapshot                 = true
  iam_database_authentication_enabled = true
  apply_immediately                   = true
  storage_encrypted = false
}

{% endhighlight %}



### Secure Example

The following example will pass the aws-neptune-enable-storage-encryption check.

{% highlight terraform %}

resource "aws_neptune_cluster" "good_example" {
  cluster_identifier                  = "neptune-cluster-demo"
  engine                              = "neptune"
  backup_retention_period             = 5
  preferred_backup_window             = "07:00-09:00"
  skip_final_snapshot                 = true
  iam_database_authentication_enabled = true
  apply_immediately                   = true
  storage_encrypted = true
}

{% endhighlight %}



### Related Links


- [https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/neptune_cluster#storage_encrypted](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/neptune_cluster#storage_encrypted){:target="_blank" rel="nofollow noreferrer noopener"}


