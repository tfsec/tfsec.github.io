---
title: azure-network-no-public-ingress - An inbound network security rule allows traffic from /0.
summary: An inbound network security rule allows traffic from /0. 
resources: [azurerm_network_security_rule] 
permalink: /docs/azure/azure-network-no-public-ingress/
---
### Explanation


Network security rules should not use very broad subnets.

Where possible, segments should be broken into smaller subnets.


### Possible Impact
The port is exposed for ingress from the internet

### Suggested Resolution
Set a more restrictive cidr range


### Insecure Example

The following example will fail the azure-network-no-public-ingress check.

{% highlight terraform %}

resource "azurerm_network_security_rule" "bad_example" {
	direction = "Inbound"
	source_address_prefix = "0.0.0.0/0"
	access = "Allow"
}
{% endhighlight %}



### Secure Example

The following example will pass the azure-network-no-public-ingress check.

{% highlight terraform %}

resource "azurerm_network_security_rule" "good_example" {
	direction = "Inbound"
	destination_address_prefix = "10.0.0.0/16"
	access = "Allow"
}
{% endhighlight %}



### Related Links


- [https://docs.microsoft.com/en-us/azure/security/fundamentals/network-best-practices](https://docs.microsoft.com/en-us/azure/security/fundamentals/network-best-practices){:target="_blank" rel="nofollow noreferrer noopener"}

- [https://www.terraform.io/docs/providers/azurerm/r/network_security_rule.html](https://www.terraform.io/docs/providers/azurerm/r/network_security_rule.html){:target="_blank" rel="nofollow noreferrer noopener"}


