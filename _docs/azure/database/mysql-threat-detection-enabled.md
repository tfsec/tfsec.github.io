---
title: azure-database-mysql-threat-detection-enabled
description: Ensure databases are not publicly accessible
shortcode: azure-database-mysql-threat-detection-enabled
legacy: 
summary: Ensure databases are not publicly accessible 
resources: [azurerm_mysql_server] 
permalink: /docs/azure/database/mysql-threat-detection-enabled/
redirect_from: 
  - /docs/azure//
---

### Explanation

My SQL server does not enable Threat Detection policy

### Possible Impact
Threat detection helps prevent compromise by alerting on threat detections

### Suggested Resolution
Enable threat detection on Mysql database


### Insecure Example

The following example will fail the azure-database-mysql-threat-detection-enabled check.

{% highlight terraform %}

resource "azurerm_mysql_server" "bad_example" {
  name                = "bad_example"

  public_network_access_enabled    = true
  ssl_enforcement_enabled          = false
  ssl_minimal_tls_version_enforced = "TLS1_2"

  threat_detection_policy {
    enabled = false
  }
}

{% endhighlight %}



### Secure Example

The following example will pass the azure-database-mysql-threat-detection-enabled check.

{% highlight terraform %}

resource "azurerm_mysql_server" "good_example" {
  name                = "good_example"

  public_network_access_enabled    = false
  ssl_enforcement_enabled          = false
  ssl_minimal_tls_version_enforced = "TLS1_2"

  threat_detection_policy {
    enabled = true
  }
}

{% endhighlight %}



### Related Links


- [https://registry.terraform.io/providers/hashicorp/azurerm/latest/docs/data-sources/mysql_server#threat_detection_policy](https://registry.terraform.io/providers/hashicorp/azurerm/latest/docs/data-sources/mysql_server#threat_detection_policy){:target="_blank" rel="nofollow noreferrer noopener"}


