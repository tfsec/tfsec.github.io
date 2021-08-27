---
title: No public access to API Gateway methods
shortcode: aws-api-gateway-no-public-access
legacy: 
summary: No public access to API Gateway methods 
resources: [aws_api_gateway_method] 
permalink: /docs/aws/api-gateway/no-public-access/
redirect_from: 
  - /docs/aws//
---

### Explanation

API Gateway methods should be protected by authorization or api key. OPTION verb calls can be used without authorization

### Possible Impact
API gateway methods can be unauthorized accessed

### Suggested Resolution
Use and authorization method or require API Key


### Insecure Example

The following example will fail the aws-api-gateway-no-public-access check.

{% highlight terraform %}

resource "aws_api_gateway_method" "bad_example" {
  rest_api_id   = aws_api_gateway_rest_api.MyDemoAPI.id
  resource_id   = aws_api_gateway_resource.MyDemoResource.id
  http_method   = "GET"
  authorization = "NONE"
}

{% endhighlight %}



### Secure Example

The following example will pass the aws-api-gateway-no-public-access check.

{% highlight terraform %}

resource "aws_api_gateway_method" "good_example" {
  rest_api_id   = aws_api_gateway_rest_api.MyDemoAPI.id
  resource_id   = aws_api_gateway_resource.MyDemoResource.id
  http_method   = "GET"
  authorization = "AWS_IAM"
}

{% endhighlight %}



### Related Links


- [https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/api_gateway_method#authorization](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/api_gateway_method#authorization){:target="_blank" rel="nofollow noreferrer noopener"}

