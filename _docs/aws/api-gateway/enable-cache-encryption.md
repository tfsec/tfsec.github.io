---
title: aws-api-gateway-enable-cache-encryption
description: API Gateway must have cache enabled
shortcode: aws-api-gateway-enable-cache-encryption
legacy: 
summary: API Gateway must have cache enabled 
resources: [aws_api_gateway_method_settings] 
permalink: /docs/aws/api-gateway/enable-cache-encryption/
redirect_from: 
  - /docs/aws//
---

### Explanation

Method cache encryption ensures that any sensitive data in the cache is not vulnerable to compromise in the event of interception

### Possible Impact
Data stored in the cache that is unencrypted may be vulnerable to compromise

### Suggested Resolution
Enable cache encryption


### Insecure Example

The following example will fail the aws-api-gateway-enable-cache-encryption check.

{% highlight terraform %}

resource "aws_api_gateway_method_settings" "bad_example" {
  rest_api_id = aws_api_gateway_rest_api.example.id
  stage_name  = aws_api_gateway_stage.example.stage_name
  method_path = "path1/GET"

  settings {
    metrics_enabled = true
    logging_level   = "INFO"
    cache_data_encrypted = false
  }
}

{% endhighlight %}



### Secure Example

The following example will pass the aws-api-gateway-enable-cache-encryption check.

{% highlight terraform %}

resource "aws_api_gateway_method_settings" "good_example" {
  rest_api_id = aws_api_gateway_rest_api.example.id
  stage_name  = aws_api_gateway_stage.example.stage_name
  method_path = "path1/GET"

  settings {
    metrics_enabled = true
    logging_level   = "INFO"
    cache_data_encrypted = true
  }
}

{% endhighlight %}



### Related Links


- [https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/api_gateway_method_settings#cache_data_encrypted](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/api_gateway_method_settings#cache_data_encrypted){:target="_blank" rel="nofollow noreferrer noopener"}


