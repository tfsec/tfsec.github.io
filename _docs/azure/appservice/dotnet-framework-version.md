---
title: azure-appservice-dotnet-framework-version
description: Azure App Service Web app does not use the latest .Net Core version
shortcode: azure-appservice-dotnet-framework-version
legacy: 
summary: Azure App Service Web app does not use the latest .Net Core version 
resources: [azurerm_app_service] 
permalink: /docs/azure/appservice/dotnet-framework-version/
redirect_from: 
  - /docs/azure//
---

### Explanation

Azure App Service web applications developed with the .NET software stack should use the latest available version of .NET to ensure the latest security fixes are in use.

### Possible Impact
Outdated .NET could contain open vulnerabilities

### Suggested Resolution
Use the latest version of the .NET framework


### Insecure Example

The following example will fail the azure-appservice-dotnet-framework-version check.

{% highlight terraform %}

resource "azurerm_app_service" "bad_example" {
  name                = "example-app-service"
  location            = azurerm_resource_group.example.location
  resource_group_name = azurerm_resource_group.example.name
  app_service_plan_id = azurerm_app_service_plan.example.id
}

{% endhighlight %}



### Secure Example

The following example will pass the azure-appservice-dotnet-framework-version check.

{% highlight terraform %}

resource "azurerm_app_service" "good_example" {
  name                = "example-app-service"
  location            = azurerm_resource_group.example.location
  resource_group_name = azurerm_resource_group.example.name
  app_service_plan_id = azurerm_app_service_plan.example.id

  site_config {
	dotnet_framework_version = "v5.0"
  }
}

{% endhighlight %}



### Related Links


- [https://registry.terraform.io/providers/hashicorp/azurerm/latest/docs/resources/app_service#dotnet_framework_version](https://registry.terraform.io/providers/hashicorp/azurerm/latest/docs/resources/app_service#dotnet_framework_version){:target="_blank" rel="nofollow noreferrer noopener"}

- [https://docs.microsoft.com/en-us/azure/app-service/configure-language-dotnetcore](https://docs.microsoft.com/en-us/azure/app-service/configure-language-dotnetcore){:target="_blank" rel="nofollow noreferrer noopener"}


