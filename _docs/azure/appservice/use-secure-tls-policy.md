---
title: Web App uses latest TLS version
shortcode: azure-appservice-use-secure-tls-policy
legacy: 
summary: Web App uses latest TLS version 
resources: [azurerm_app_service] 
permalink: /docs/azure/appservice/use-secure-tls-policy/
redirect_from: 
  - /docs/azure//
---

### Explanation

Use a more recent TLS/SSL policy for the App Service

### Possible Impact
The minimum TLS version for apps should be TLS1_2

### Suggested Resolution
The TLS version being outdated and has known vulnerabilities


### Insecure Example

The following example will fail the azure-appservice-use-secure-tls-policy check.

{% highlight terraform %}

resource "azurerm_app_service" "bad_example" {
  name                = "example-app-service"
  location            = azurerm_resource_group.example.location
  resource_group_name = azurerm_resource_group.example.name
  app_service_plan_id = azurerm_app_service_plan.example.id

  site_config {
	  min_tls_version = "1.0"
  }
}

{% endhighlight %}



### Secure Example

The following example will pass the azure-appservice-use-secure-tls-policy check.

{% highlight terraform %}

resource "azurerm_app_service" "good_example" {
  name                = "example-app-service"
  location            = azurerm_resource_group.example.location
  resource_group_name = azurerm_resource_group.example.name
  app_service_plan_id = azurerm_app_service_plan.example.id
}

{% endhighlight %}



### Related Links


- [https://registry.terraform.io/providers/hashicorp/azurerm/latest/docs/resources/app_service#min_tls_version](https://registry.terraform.io/providers/hashicorp/azurerm/latest/docs/resources/app_service#min_tls_version){:target="_blank" rel="nofollow noreferrer noopener"}


