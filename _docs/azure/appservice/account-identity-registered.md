---
title: azure-appservice-account-identity-registered
description: Web App has registration with AD enabled
shortcode: azure-appservice-account-identity-registered
legacy: 
summary: Web App has registration with AD enabled 
resources: [azurerm_app_service] 
permalink: /docs/azure/appservice/account-identity-registered/
redirect_from: 
  - /docs/azure//
---

### Explanation

Registering the identity used by an App with AD allows it to interact with other services without using username and password

### Possible Impact
Interaction between services can't easily be achieved without username/password

### Suggested Resolution
Register the app identity with AD


### Insecure Example

The following example will fail the azure-appservice-account-identity-registered check.

{% highlight terraform %}

resource "azurerm_app_service" "bad_example" {
  name                = "example-app-service"
  location            = azurerm_resource_group.example.location
  resource_group_name = azurerm_resource_group.example.name
  app_service_plan_id = azurerm_app_service_plan.example.id
}

{% endhighlight %}



### Secure Example

The following example will pass the azure-appservice-account-identity-registered check.

{% highlight terraform %}

resource "azurerm_app_service" "good_example" {
  name                = "example-app-service"
  location            = azurerm_resource_group.example.location
  resource_group_name = azurerm_resource_group.example.name
  app_service_plan_id = azurerm_app_service_plan.example.id

  identity {
    type = "UserAssigned"
    identity_ids = "webapp1"
  }
}

{% endhighlight %}



### Related Links


- [https://registry.terraform.io/providers/hashicorp/azurerm/latest/docs/resources/app_service#identity](https://registry.terraform.io/providers/hashicorp/azurerm/latest/docs/resources/app_service#identity){:target="_blank" rel="nofollow noreferrer noopener"}


