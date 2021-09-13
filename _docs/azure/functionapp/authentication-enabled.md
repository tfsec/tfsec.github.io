---
title: Function App authentication is activated
shortcode: azure-functionapp-authentication-enabled
legacy: 
summary: Function App authentication is activated 
resources: [azurerm_function_app] 
permalink: /docs/azure/functionapp/authentication-enabled/
redirect_from: 
  - /docs/azure//
---

### Explanation

Enabling authentication ensures that all communications in the application are authenticated. The auth_settings block needs to be filled out with the appropriate auth backend settings

### Possible Impact
Anonymous HTTP requests will be accepted

### Suggested Resolution
Enable authentication to prevent anonymous request being accepted


### Insecure Example

The following example will fail the azure-functionapp-authentication-enabled check.

{% highlight terraform %}

resource "azurerm_function_app" "bad_example" {
  name                = "example-function-app"
  location            = azurerm_resource_group.example.location
  resource_group_name = azurerm_resource_group.example.name
  app_service_plan_id = azurerm_function_app_plan.example.id
}

{% endhighlight %}



### Secure Example

The following example will pass the azure-functionapp-authentication-enabled check.

{% highlight terraform %}

resource "azurerm_function_app" "good_example" {
  name                = "example-function-app"
  location            = azurerm_resource_group.example.location
  resource_group_name = azurerm_resource_group.example.name
  app_service_plan_id = azurerm_function_app_plan.example.id

  auth_settings {
    enabled = true
  }
}

{% endhighlight %}



### Related Links


- [https://registry.terraform.io/providers/hashicorp/azurerm/latest/docs/resources/function_app#enabled](https://registry.terraform.io/providers/hashicorp/azurerm/latest/docs/resources/function_app#enabled){:target="_blank" rel="nofollow noreferrer noopener"}

