---
title: Ensure databases are not publicly accessible
shortcode: azure-database-no-public-access
legacy: 
summary: Ensure databases are not publicly accessible 
resources: [azurerm_mariadb_server azurerm_mssql_server azurerm_mysql_server azurerm_postgresql_server] 
permalink: /docs/azure/database/no-public-access/
redirect_from: 
  - /docs/azure//
---

### Explanation

Database resources should not publicly available. You should limit all access to the minimum that is required for your application to function.

### Possible Impact
Publicly accessible database could lead to compromised data

### Suggested Resolution
Disable public access to database when not required


### Insecure Example

The following example will fail the azure-database-no-public-access check.

{% highlight terraform %}

resource "azurerm_postgresql_server" "bad_example" {
  name                = "bad_example"

  public_network_access_enabled    = true
  ssl_enforcement_enabled          = false
  ssl_minimal_tls_version_enforced = "TLS1_2"
}

{% endhighlight %}



### Secure Example

The following example will pass the azure-database-no-public-access check.

{% highlight terraform %}

resource "azurerm_postgresql_server" "good_example" {
  name                = "bad_example"

  public_network_access_enabled    = false
  ssl_enforcement_enabled          = false
  ssl_minimal_tls_version_enforced = "TLS1_2"
}

{% endhighlight %}



### Related Links


- [https://registry.terraform.io/providers/hashicorp/azurerm/latest/docs/resources/postgresql_server#public_network_access_enabled](https://registry.terraform.io/providers/hashicorp/azurerm/latest/docs/resources/postgresql_server#public_network_access_enabled){:target="_blank" rel="nofollow noreferrer noopener"}

- [https://registry.terraform.io/providers/hashicorp/azurerm/latest/docs/resources/mysql_server#public_network_access_enabled](https://registry.terraform.io/providers/hashicorp/azurerm/latest/docs/resources/mysql_server#public_network_access_enabled){:target="_blank" rel="nofollow noreferrer noopener"}

- [https://registry.terraform.io/providers/hashicorp/azurerm/latest/docs/resources/mariadb_server#public_network_access_enabled](https://registry.terraform.io/providers/hashicorp/azurerm/latest/docs/resources/mariadb_server#public_network_access_enabled){:target="_blank" rel="nofollow noreferrer noopener"}


