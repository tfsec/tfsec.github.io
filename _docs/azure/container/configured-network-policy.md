---
title: Ensure AKS cluster has Network Policy configured
shortcode: azure-container-configured-network-policy
legacy: AZU006
summary: Ensure AKS cluster has Network Policy configured 
resources: [azurerm_kubernetes_cluster] 
permalink: /docs/azure/container/configured-network-policy/
redirect_from: 
  - /docs/azure/AZU006/
---

### Explanation


The Kubernetes object type NetworkPolicy should be defined to have opportunity allow or block traffic to pods, as in a Kubernetes cluster configured with default settings, all pods can discover and communicate with each other without any restrictions.


### Possible Impact
No network policy is protecting the AKS cluster

### Suggested Resolution
Configure a network policy


### Insecure Example

The following example will fail the azure-container-configured-network-policy check.

{% highlight terraform %}

resource "azurerm_kubernetes_cluster" "bad_example" {
	network_profile {
	  }
}

{% endhighlight %}



### Secure Example

The following example will pass the azure-container-configured-network-policy check.

{% highlight terraform %}

resource "azurerm_kubernetes_cluster" "good_example" {
	network_profile {
	  network_policy = "calico"
	  }
}

{% endhighlight %}



### Related Links


- [https://registry.terraform.io/providers/hashicorp/azurerm/latest/docs/resources/kubernetes_cluster#network_policy](https://registry.terraform.io/providers/hashicorp/azurerm/latest/docs/resources/kubernetes_cluster#network_policy){:target="_blank" rel="nofollow noreferrer noopener"}

- [https://kubernetes.io/docs/concepts/services-networking/network-policies](https://kubernetes.io/docs/concepts/services-networking/network-policies){:target="_blank" rel="nofollow noreferrer noopener"}


