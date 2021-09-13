---
title: App service does not enable HTTP logging
shortcode: azure-appservice-http-logs-enabled
legacy: 
summary: App service does not enable HTTP logging 
resources: [azurerm_app_service] 
permalink: /docs/azure/appservice/http-logs-enabled/
redirect_from: 
  - /docs/azure//
---

### Explanation

Raw HTTP request data in the W3C extended log file format. Each log message includes data such as the HTTP method, resource URI, client IP, client port, user agent, response code, and so on.

### Possible Impact
Missed logs related to HTTP requests

### Suggested Resolution
Enable http_logs


### Insecure Example

The following example will fail the azure-appservice-http-logs-enabled check.

{% highlight terraform %}

resource "azurerm_app_service" "bad_example" {
  name                = "example-app-service"
  location            = azurerm_resource_group.example.location
  resource_group_name = azurerm_resource_group.example.name
  app_service_plan_id = azurerm_app_service_plan.example.id
}

{% endhighlight %}



### Secure Example

The following example will pass the azure-appservice-http-logs-enabled check.

{% highlight terraform %}

resource "azurerm_app_service" "good_example" {
  name                = "example-app-service"
  location            = azurerm_resource_group.example.location
  resource_group_name = azurerm_resource_group.example.name
  app_service_plan_id = azurerm_app_service_plan.example.id
  logs {
    http_logs {
      retention_in_days = 4
      retention_in_mb = 10
    }
  }
}

{% endhighlight %}



### Related Links


- [https://registry.terraform.io/providers/hashicorp/azurerm/latest/docs/resources/app_service#http_logs](https://registry.terraform.io/providers/hashicorp/azurerm/latest/docs/resources/app_service#http_logs){:target="_blank" rel="nofollow noreferrer noopener"}

- [https://docs.microsoft.com/en-us/azure/app-service/troubleshoot-diagnostic-logs](https://docs.microsoft.com/en-us/azure/app-service/troubleshoot-diagnostic-logs){:target="_blank" rel="nofollow noreferrer noopener"}

