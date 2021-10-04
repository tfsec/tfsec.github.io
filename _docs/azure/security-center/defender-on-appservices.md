---
title: azure-security-center-defender-on-appservices
description: Ensure Azure Defender is set to On for container registries
shortcode: azure-security-center-defender-on-appservices
legacy: 
summary: Ensure Azure Defender is set to On for container registries 
resources: [azurerm_security_center_subscription_pricing] 
permalink: /docs/azure/security-center/defender-on-appservices/
redirect_from: 
  - /docs/azure//
---

### Explanation

Azure Defender is a cloud workload protection service that utilizes and agent-based deployment to analyze signals from Azure network fabric and the service control plane, to detect threats across all Azure resources. It can also analyze non-Azure resources, utilizing Azure Arc, including those on-premises and in both AWS and GCP (once they've been onboarded).

### Possible Impact
Azure Defender for App Service detects attacks targeting applications running over App Service.

### Suggested Resolution
Enable AppServices in Azure Defender


### Insecure Example

The following example will fail the azure-security-center-defender-on-appservices check.

{% highlight terraform %}

resource "azurerm_security_center_subscription_pricing" "bad_example" {
  tier          = "Free"
  resource_type = "VirtualMachines"
}

{% endhighlight %}



### Secure Example

The following example will pass the azure-security-center-defender-on-appservices check.

{% highlight terraform %}

resource "azurerm_security_center_subscription_pricing" "good_example" {
  tier          = "Standard"
  resource_type = "VirtualMachines,AppServices"
}

{% endhighlight %}



### Related Links


- [https://registry.terraform.io/providers/hashicorp/azurerm/latest/docs/resources/security_center_subscription_pricing#resource_type](https://registry.terraform.io/providers/hashicorp/azurerm/latest/docs/resources/security_center_subscription_pricing#resource_type){:target="_blank" rel="nofollow noreferrer noopener"}

- [https://docs.microsoft.com/en-us/azure/security-center/defender-for-app-service-introduction](https://docs.microsoft.com/en-us/azure/security-center/defender-for-app-service-introduction){:target="_blank" rel="nofollow noreferrer noopener"}

