---
title: aws-elastic-search-enable-in-transit-encryption
description: Elasticsearch domain uses plaintext traffic for node to node communication.
shortcode: aws-elastic-search-enable-in-transit-encryption
legacy: AWS032
summary: Elasticsearch domain uses plaintext traffic for node to node communication. 
resources: [aws_elasticsearch_domain] 
permalink: /docs/aws/elastic-search/enable-in-transit-encryption/
redirect_from: 
  - /docs/aws/AWS032/
---

### Explanation


Traffic flowing between Elasticsearch nodes should be encrypted to ensure sensitive data is kept private.


### Possible Impact
In transit data between nodes could be read if intercepted

### Suggested Resolution
Enable encrypted node to node communication


### Insecure Example

The following example will fail the aws-elastic-search-enable-in-transit-encryption check.

{% highlight terraform %}

resource "aws_elasticsearch_domain" "bad_example" {
  domain_name = "domain-foo"

  node_to_node_encryption {
    enabled = false
  }
}

{% endhighlight %}



### Secure Example

The following example will pass the aws-elastic-search-enable-in-transit-encryption check.

{% highlight terraform %}

resource "aws_elasticsearch_domain" "good_example" {
  domain_name = "domain-foo"

  node_to_node_encryption {
    enabled = true
  }
}

{% endhighlight %}



### Related Links


- [https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/elasticsearch_domain#encrypt_at_rest](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/elasticsearch_domain#encrypt_at_rest){:target="_blank" rel="nofollow noreferrer noopener"}

- [https://docs.aws.amazon.com/elasticsearch-service/latest/developerguide/ntn.html](https://docs.aws.amazon.com/elasticsearch-service/latest/developerguide/ntn.html){:target="_blank" rel="nofollow noreferrer noopener"}


