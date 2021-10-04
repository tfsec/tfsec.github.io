---
title: azure-authorization-limit-role-actions
description: Roles limited to the required actions
shortcode: azure-authorization-limit-role-actions
legacy: 
summary: Roles limited to the required actions 
resources: [azurerm_role_definition] 
permalink: /docs/azure/authorization/limit-role-actions/
redirect_from: 
  - /docs/azure//
---

### Explanation

The permissions granted to a role should be kept to the minimum required to be able to do the task. Wildcard permissions must not be used.

### Possible Impact
Open permissions for subscriptions could result in an easily compromisable account

### Suggested Resolution
Use targeted permissions for roles


### Insecure Example

The following example will fail the azure-authorization-limit-role-actions check.

{% highlight terraform %}

data "azurerm_subscription" "primary" {
}

resource "azurerm_role_definition" "example" {
  name        = "my-custom-role"
  scope       = data.azurerm_subscription.primary.id
  description = "This is a custom role created via Terraform"

  permissions {
    actions     = ["*"]
    not_actions = []
  }

  assignable_scopes = [
    "/"
  ]
}

{% endhighlight %}



### Secure Example

The following example will pass the azure-authorization-limit-role-actions check.

{% highlight terraform %}

data "azurerm_subscription" "primary" {
}

resource "azurerm_role_definition" "example" {
  name        = "my-custom-role"
  scope       = data.azurerm_subscription.primary.id
  description = "This is a custom role created via Terraform"

  permissions {
    actions     = ["*"]
    not_actions = []
  }

  assignable_scopes = [
    data.azurerm_subscription.primary.id,
  ]
}

{% endhighlight %}



### Related Links


- [https://registry.terraform.io/providers/hashicorp/azurerm/latest/docs/resources/role_definition#actions](https://registry.terraform.io/providers/hashicorp/azurerm/latest/docs/resources/role_definition#actions){:target="_blank" rel="nofollow noreferrer noopener"}


