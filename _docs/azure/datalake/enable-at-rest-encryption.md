---
title: azure-datalake-enable-at-rest-encryption
description: Unencrypted data lake storage.
shortcode: azure-datalake-enable-at-rest-encryption
legacy: AZU004
summary: Unencrypted data lake storage. 
resources: [azurerm_data_lake_store] 
permalink: /docs/azure/datalake/enable-at-rest-encryption/
redirect_from: 
  - /docs/azure/AZU004/
---

### Explanation


Datalake storage encryption defaults to Enabled, it shouldn't be overridden to Disabled.


### Possible Impact
Data could be read if compromised

### Suggested Resolution
Enable encryption of data lake storage


### Insecure Example

The following example will fail the azure-datalake-enable-at-rest-encryption check.

{% highlight terraform %}

resource "azurerm_data_lake_store" "bad_example" {
	encryption_state = "Disabled"
}
{% endhighlight %}



### Secure Example

The following example will pass the azure-datalake-enable-at-rest-encryption check.

{% highlight terraform %}

resource "azurerm_data_lake_store" "good_example" {
	encryption_state = "Enabled"
}
{% endhighlight %}



### Related Links


- [https://registry.terraform.io/providers/hashicorp/azurerm/latest/docs/resources/data_lake_store](https://registry.terraform.io/providers/hashicorp/azurerm/latest/docs/resources/data_lake_store){:target="_blank" rel="nofollow noreferrer noopener"}

- [https://docs.microsoft.com/en-us/azure/data-lake-store/data-lake-store-security-overview](https://docs.microsoft.com/en-us/azure/data-lake-store/data-lake-store-security-overview){:target="_blank" rel="nofollow noreferrer noopener"}


