---
title: azure-storage-container-activity-logs-not-public
description: Ensure public access level for Blob Containers is set to private
shortcode: azure-storage-container-activity-logs-not-public
legacy: 
summary: Ensure public access level for Blob Containers is set to private 
resources: [azurerm_storage_container] 
permalink: /docs/azure/storage/container-activity-logs-not-public/
redirect_from: 
  - /docs/azure//
---

### Explanation


			Anonymous, public read access to a container and its blobs can be enabled in Azure Blob storage. It grants read-only access to these resources without sharing the account key or requiring a shared access signature.

			We recommend you do not provide anonymous access to blob containers until, and unless, it is strongly desired. A shared access signature token should be used for providing controlled and timed access to blob containers.

### Possible Impact
Data in the storage container could be exposed publicly

### Suggested Resolution
Disable public access to storage containers


### Insecure Example

The following example will fail the azure-storage-container-activity-logs-not-public check.

{% highlight terraform %}

resource "azurerm_storage_container" "bad_example" {
	name                  = "terraform-container-storage"
	container_access_type = "public"
}

{% endhighlight %}



### Secure Example

The following example will pass the azure-storage-container-activity-logs-not-public check.

{% highlight terraform %}

resource "azurerm_storage_container" "good_example" {
	name                  = "terraform-container-storage"
	container_access_type = "private"
}

{% endhighlight %}



### Related Links


- [https://registry.terraform.io/providers/hashicorp/azurerm/latest/docs/resources/storage_container#container_access_type](https://registry.terraform.io/providers/hashicorp/azurerm/latest/docs/resources/storage_container#container_access_type){:target="_blank" rel="nofollow noreferrer noopener"}


