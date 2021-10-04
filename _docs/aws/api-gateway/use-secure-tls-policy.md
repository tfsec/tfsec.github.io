---
title: aws-api-gateway-use-secure-tls-policy
description: API Gateway domain name uses outdated SSL/TLS protocols.
shortcode: aws-api-gateway-use-secure-tls-policy
legacy: AWS025
summary: API Gateway domain name uses outdated SSL/TLS protocols. 
resources: [aws_api_gateway_domain_name] 
permalink: /docs/aws/api-gateway/use-secure-tls-policy/
redirect_from: 
  - /docs/aws/AWS025/
---

### Explanation


You should not use outdated/insecure TLS versions for encryption. You should be using TLS v1.2+.


### Possible Impact
Outdated SSL policies increase exposure to known vulnerabilities

### Suggested Resolution
Use the most modern TLS/SSL policies available


### Insecure Example

The following example will fail the aws-api-gateway-use-secure-tls-policy check.

{% highlight terraform %}

resource "aws_api_gateway_domain_name" "bad_example" {
	security_policy = "TLS_1_0"
}

{% endhighlight %}



### Secure Example

The following example will pass the aws-api-gateway-use-secure-tls-policy check.

{% highlight terraform %}

resource "aws_api_gateway_domain_name" "good_example" {
	security_policy = "TLS_1_2"
}

{% endhighlight %}



### Related Links


- [https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/api_gateway_domain_name#security_policy](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/api_gateway_domain_name#security_policy){:target="_blank" rel="nofollow noreferrer noopener"}

- [https://docs.aws.amazon.com/apigateway/latest/developerguide/apigateway-custom-domain-tls-version.html](https://docs.aws.amazon.com/apigateway/latest/developerguide/apigateway-custom-domain-tls-version.html){:target="_blank" rel="nofollow noreferrer noopener"}


