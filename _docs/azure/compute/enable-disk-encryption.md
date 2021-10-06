---
title: Enable disk encryption on managed disk
shortcode: azure-compute-enable-disk-encryption
legacy: AZU003
summary: Enable disk encryption on managed disk 
resources: [azurerm_managed_disk] 
permalink: /docs/azure/compute/enable-disk-encryption/
redirect_from: 
  - /docs/azure/AZU003/
---

### Explanation


Manage disks should be encrypted at rest. When specifying the <code>encryption_settings</code> block, the enabled attribute should be set to <code>true</code>.


### Possible Impact
Data could be read if compromised

### Suggested Resolution
Enable encryption on managed disks


### Insecure Example

The following example will fail the azure-compute-enable-disk-encryption check.

{% highlight terraform %}

resource "azurerm_managed_disk" "bad_example" {
	encryption_settings {
		enabled = false
	}
}
{% endhighlight %}



### Secure Example

The following example will pass the azure-compute-enable-disk-encryption check.

{% highlight terraform %}

resource "azurerm_managed_disk" "good_example" {
	encryption_settings {
		enabled = true
	}
}
{% endhighlight %}



### Related Links


- [https://registry.terraform.io/providers/hashicorp/azurerm/latest/docs/resources/managed_disk](https://registry.terraform.io/providers/hashicorp/azurerm/latest/docs/resources/managed_disk){:target="_blank" rel="nofollow noreferrer noopener"}

- [https://docs.microsoft.com/en-us/azure/virtual-machines/linux/disk-encryption](https://docs.microsoft.com/en-us/azure/virtual-machines/linux/disk-encryption){:target="_blank" rel="nofollow noreferrer noopener"}


