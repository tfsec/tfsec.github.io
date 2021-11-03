---
title: Ensure App Service can only be accessed via HTTPS. The default is false
shortcode: azure-appservice-enable-https-only
legacy: 
summary: Ensure App Service can only be accessed via HTTPS. The default is false 
resources: [azurerm_app_service] 
permalink: /docs/azure/appservice/enable-https-only/
redirect_from: 
  - /docs/azure//
---

### Explanation

By default, clients can connect to App Service by using both HTTP or HTTPS. HTTP should be disabled enabling the HTTPS Only setting.

### Possible Impact
Anyone can access App Service using HTTP.

### Suggested Resolution
Enable HTTPS only


### Insecure Example

The following example will fail the azure-appservice-enable-https-only check.

{% highlight terraform %}

      resource "azurerm_app_service" "bad_example" {
        name                       = "example-app-service"
        location                   = azurerm_resource_group.example.location
        resource_group_name        = azurerm_resource_group.example.name
        app_service_plan_id        = azurerm_app_service_plan.example.id
      }
      
{% endhighlight %}



### Secure Example

The following example will pass the azure-appservice-enable-https-only check.

{% highlight terraform %}
resource "azurerm_app_service" "good_example" {
        name                       = "example-app-service"
        location                   = azurerm_resource_group.example.location
        resource_group_name        = azurerm_resource_group.example.name
        app_service_plan_id        = azurerm_app_service_plan.example.id
        https_only                 = true
      }
{% endhighlight %}



### Related Links


- [https://registry.terraform.io/providers/hashicorp/azurerm/latest/docs/resources/app_service#https_only](https://registry.terraform.io/providers/hashicorp/azurerm/latest/docs/resources/app_service#https_only){:target="_blank" rel="nofollow noreferrer noopener"}

- [https://docs.microsoft.com/en-us/azure/app-service/configure-ssl-bindings#enforce-https](https://docs.microsoft.com/en-us/azure/app-service/configure-ssl-bindings#enforce-https){:target="_blank" rel="nofollow noreferrer noopener"}


