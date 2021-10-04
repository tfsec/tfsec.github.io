---
title: azure-monitor-capture-all-regions
description: Ensure activitys are captured for all locations
shortcode: azure-monitor-capture-all-regions
legacy: 
summary: Ensure activitys are captured for all locations 
resources: [azurerm_monitor_log_profile] 
permalink: /docs/azure/monitor/capture-all-regions/
redirect_from: 
  - /docs/azure//
---

### Explanation

Log profiles should capture all regions to ensure that all events are logged

### Possible Impact
Activity may be occurring in locations that aren't being monitored

### Suggested Resolution
Enable capture for all locations


### Insecure Example

The following example will fail the azure-monitor-capture-all-regions check.

{% highlight terraform %}


resource "azurerm_monitor_log_profile" "bad_example" {
  name = "bad_example"

  categories = []

  locations = [
    "westus",
    "global",
  ]

  retention_policy {
    enabled = true
    days    = 7
  }
}

{% endhighlight %}



### Secure Example

The following example will pass the azure-monitor-capture-all-regions check.

{% highlight terraform %}

resource "azurerm_monitor_log_profile" "bad_example" {
  name = "bad_example"

  categories = []

  locations = [
	"eastus",
	"eastus2",
	"southcentralus",
	"westus2",
	"westus3",
	"australiaeast",
	"southeastasia",
	"northeurope",
	"swedencentral",
	"uksouth",
	"westeurope",
	"centralus",
	"northcentralus",
	"westus",
	"southafricanorth",
	"centralindia",
	"eastasia",
	"japaneast",
	"jioindiawest",
	"koreacentral",
	"canadacentral",
	"francecentral",
	"germanywestcentral",
	"norwayeast",
	"switzerlandnorth",
	"uaenorth",
	"brazilsouth",
	"centralusstage",
	"eastusstage",
	"eastus2stage",
	"northcentralusstage",
	"southcentralusstage",
	"westusstage",
	"westus2stage",
	"asia",
	"asiapacific",
	"australia",
	"brazil",
	"canada",
	"europe",
	"global",
	"india",
	"japan",
	"uk",
	"unitedstates",
	"eastasiastage",
	"southeastasiastage",
	"centraluseuap",
	"eastus2euap",
	"westcentralus",
	"southafricawest",
	"australiacentral",
	"australiacentral2",
	"australiasoutheast",
	"japanwest",
	"jioindiacentral",
	"koreasouth",
	"southindia",
	"westindia",
	"canadaeast",
	"francesouth",
	"germanynorth",
	"norwaywest",
	"swedensouth",
	"switzerlandwest",
	"ukwest",
	"uaecentral",
	"brazilsoutheast",
  ]

  retention_policy {
    enabled = true
    days    = 7
  }
}

			
{% endhighlight %}



### Related Links


- [https://registry.terraform.io/providers/hashicorp/azurerm/latest/docs/resources/monitor_log_profile#locations](https://registry.terraform.io/providers/hashicorp/azurerm/latest/docs/resources/monitor_log_profile#locations){:target="_blank" rel="nofollow noreferrer noopener"}

- [https://docs.microsoft.com/en-us/cli/azure/monitor/log-profiles?view=azure-cli-latest#az_monitor_log_profiles_create-required-parameters](https://docs.microsoft.com/en-us/cli/azure/monitor/log-profiles?view=azure-cli-latest#az_monitor_log_profiles_create-required-parameters){:target="_blank" rel="nofollow noreferrer noopener"}


