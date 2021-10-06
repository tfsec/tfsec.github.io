---
title: Web App uses the latest HTTP version
shortcode: azure-appservice-enable-http2
legacy: 
summary: Web App uses the latest HTTP version 
resources: [azurerm_app_service] 
permalink: /docs/azure/appservice/enable-http2/
redirect_from: 
  - /docs/azure//
---

### Explanation

Use the latest version of HTTP to ensure you are benefiting from security fixes

### Possible Impact
Outdated versions of HTTP has security vulnerabilities

### Suggested Resolution
Use the latest version of HTTP


### Insecure Example

The following example will fail the azure-appservice-enable-http2 check.

{% highlight terraform %}

resource "azurerm_app_service" "bad_example" {
  name                = "example-app-service"
  location            = azurerm_resource_group.example.location
  resource_group_name = azurerm_resource_group.example.name
  app_service_plan_id = azurerm_app_service_plan.example.id
}

{% endhighlight %}



### Secure Example

The following example will pass the azure-appservice-enable-http2 check.

{% highlight terraform %}

resource "azurerm_app_service" "good_example" {
  name                = "example-app-service"
  location            = azurerm_resource_group.example.location
  resource_group_name = azurerm_resource_group.example.name
  app_service_plan_id = azurerm_app_service_plan.example.id

  site_config {
	  http2_enabled = true
  }
}

{% endhighlight %}



### Related Links


- [https://registry.terraform.io/providers/hashicorp/azurerm/latest/docs/resources/app_service#http2_enabled](https://registry.terraform.io/providers/hashicorp/azurerm/latest/docs/resources/app_service#http2_enabled){:target="_blank" rel="nofollow noreferrer noopener"}


