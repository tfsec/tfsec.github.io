---
title: azure-compute-no-secrets-in-custom-data - Custom data for virtual machines must not contain sensitive data
summary: Custom data for virtual machines must not contain sensitive data 
resources: [azurerm_virtual_machine] 
permalink: /docs/azure/azure-compute-no-secrets-in-custom-data/
---
### Explanation

	

### Possible Impact
 Custom data with secrets can lead to compomised credentials

### Suggested Resolution
Remove sensitive data from custom data


### Insecure Example

The following example will fail the azure-compute-no-secrets-in-custom-data check.

{% highlight terraform %}

			// bad example code here
			
{% endhighlight %}



### Secure Example

The following example will pass the azure-compute-no-secrets-in-custom-data check.

{% highlight terraform %}

			// good example code here
			
{% endhighlight %}



