---
title: Ensure AKS has an API Server Authorized IP Ranges enabled
shortcode: azure-container-limit-authorized-ips
legacy: AZU008
summary: Ensure AKS has an API Server Authorized IP Ranges enabled 
resources: [azurerm_kubernetes_cluster] 
permalink: /docs/azure/container/limit-authorized-ips/
redirect_from: 
  - /docs/azure/AZU008/
---

### Explanation


The API server is the central way to interact with and manage a cluster. To improve cluster security and minimize attacks, the API server should only be accessible from a limited set of IP address ranges.


### Possible Impact
Any IP can interact with the API server

### Suggested Resolution
Limit the access to the API server to a limited IP range


### Insecure Example

The following example will fail the azure-container-limit-authorized-ips check.

{% highlight terraform %}

resource "azurerm_kubernetes_cluster" "bad_example" {

}

{% endhighlight %}



### Secure Example

The following example will pass the azure-container-limit-authorized-ips check.

{% highlight terraform %}

resource "azurerm_kubernetes_cluster" "good_example" {
    api_server_authorized_ip_ranges = [
		"1.2.3.4/32"
	]
}

{% endhighlight %}



### Related Links


- [https://registry.terraform.io/providers/hashicorp/azurerm/latest/docs/resources/kubernetes_cluster#api_server_authorized_ip_ranges](https://registry.terraform.io/providers/hashicorp/azurerm/latest/docs/resources/kubernetes_cluster#api_server_authorized_ip_ranges){:target="_blank" rel="nofollow noreferrer noopener"}

- [https://docs.microsoft.com/en-us/azure/aks/api-server-authorized-ip-ranges](https://docs.microsoft.com/en-us/azure/aks/api-server-authorized-ip-ranges){:target="_blank" rel="nofollow noreferrer noopener"}


