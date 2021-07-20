---
title: azure-container-logging - Ensure AKS logging to Azure Monitoring is Configured
summary: Ensure AKS logging to Azure Monitoring is Configured 
resources: [azurerm_kubernetes_cluster] 
permalink: /docs/azure/azure-container-logging/
---
### Explanation


Ensure AKS logging to Azure Monitoring is configured for containers to monitor the performance of workloads.


### Possible Impact
Logging provides valuable information about access and usage

### Suggested Resolution
Enable logging for AKS


### Insecure Example

The following example will fail the azure-container-logging check.

{% highlight terraform %}

resource "azurerm_kubernetes_cluster" "bad_example" {
    addon_profile {}
}

{% endhighlight %}



### Secure Example

The following example will pass the azure-container-logging check.

{% highlight terraform %}

resource "azurerm_kubernetes_cluster" "good_example" {
    addon_profile {
		oms_agent {
			enabled = true
		}
	}
}

{% endhighlight %}



### Related Links


- [https://www.terraform.io/docs/providers/azurerm/r/kubernetes_cluster.html#oms_agent](https://www.terraform.io/docs/providers/azurerm/r/kubernetes_cluster.html#oms_agent){:target="_blank" rel="nofollow noreferrer noopener"}

- [https://docs.microsoft.com/en-us/azure/azure-monitor/insights/container-insights-onboard](https://docs.microsoft.com/en-us/azure/azure-monitor/insights/container-insights-onboard){:target="_blank" rel="nofollow noreferrer noopener"}


