---
title: aws-rds-no-public-db-access - A database resource is marked as publicly accessible.
summary: A database resource is marked as publicly accessible. 
resources: [aws_db_instance aws_dms_replication_instance aws_rds_cluster_instance aws_redshift_cluster] 
permalink: /docs/aws/aws-rds-no-public-db-access/
---
### Explanation


Database resources should not publicly available. You should limit all access to the minimum that is required for your application to function. 


### Possible Impact
The database instance is publicly accessible

### Suggested Resolution
Set the database to not be publicly accessible


### Insecure Example

The following example will fail the aws-rds-no-public-db-access check.

{% highlight terraform %}

resource "aws_db_instance" "bad_example" {
	publicly_accessible = true
}

{% endhighlight %}



### Secure Example

The following example will pass the aws-rds-no-public-db-access check.

{% highlight terraform %}

resource "aws_db_instance" "good_example" {
	publicly_accessible = false
}

{% endhighlight %}



### Related Links


- [https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/db_instance](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/db_instance){:target="_blank" rel="nofollow noreferrer noopener"}


