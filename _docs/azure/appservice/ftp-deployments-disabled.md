---
title: Ensure FTP Deployments are disabled
shortcode: azure-appservice-ftp-deployments-disabled
legacy: 
summary: Ensure FTP Deployments are disabled 
resources: [azurerm_app_service] 
permalink: /docs/azure/appservice/ftp-deployments-disabled/
redirect_from: 
  - /docs/azure//
---

### Explanation

FTPS (Secure FTP) is used to enhance security for Azure web application using App Service as it adds an extra layer of security to the FTP protocol, and help you to comply with the industry standards and regulations. For enhanced security, it is highly advices to use FTP over TLS/SSL only. You can also disable both FTP and FTPS if you don't use FTP deployment.

### Possible Impact
FTP is insecure and can lead to loss of data

### Suggested Resolution
Disable FTP


### Insecure Example

The following example will fail the azure-appservice-ftp-deployments-disabled check.

{% highlight terraform %}

resource "azurerm_app_service" "bad_example" {
  name                = "example-app-service"
  location            = azurerm_resource_group.example.location
  resource_group_name = azurerm_resource_group.example.name
  app_service_plan_id = azurerm_app_service_plan.example.id
}

{% endhighlight %}



### Secure Example

The following example will pass the azure-appservice-ftp-deployments-disabled check.

{% highlight terraform %}

resource "azurerm_app_service" "good_example" {
  name                = "example-app-service"
  location            = azurerm_resource_group.example.location
  resource_group_name = azurerm_resource_group.example.name
  app_service_plan_id = azurerm_app_service_plan.example.id
  ftps_state = "Disabled"
}

{% endhighlight %}



### Related Links


- [https://registry.terraform.io/providers/hashicorp/azurerm/latest/docs/resources/app_service#ftps_state](https://registry.terraform.io/providers/hashicorp/azurerm/latest/docs/resources/app_service#ftps_state){:target="_blank" rel="nofollow noreferrer noopener"}

- [https://docs.microsoft.com/en-us/azure/app-service/deploy-ftp](https://docs.microsoft.com/en-us/azure/app-service/deploy-ftp){:target="_blank" rel="nofollow noreferrer noopener"}


