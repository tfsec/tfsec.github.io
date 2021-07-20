---
title: azure-datalake-enable-at-rest-encryption - Unencrypted data lake storage.
summary: Unencrypted data lake storage. 
resources: [azurerm_data_lake_store] 
permalink: /docs/azure/azure-datalake-enable-at-rest-encryption/
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


- [https://docs.microsoft.com/en-us/azure/data-lake-store/data-lake-store-security-overview](https://docs.microsoft.com/en-us/azure/data-lake-store/data-lake-store-security-overview){:target="_blank" rel="nofollow noreferrer noopener"}

- [https://www.terraform.io/docs/providers/azurerm/r/data_lake_store.html](https://www.terraform.io/docs/providers/azurerm/r/data_lake_store.html){:target="_blank" rel="nofollow noreferrer noopener"}


