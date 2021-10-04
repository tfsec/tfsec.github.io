---
title: google-iam-no-folder-level-service-account-impersonation
description: Users should not be granted service account access at the folder level
shortcode: google-iam-no-folder-level-service-account-impersonation
legacy: 
summary: Users should not be granted service account access at the folder level 
resources: [google_folder_iam_binding google_folder_iam_member] 
permalink: /docs/google/iam/no-folder-level-service-account-impersonation/
redirect_from: 
  - /docs/google//
---

### Explanation

Users with service account access at folder level can impersonate any service account. Instead, they should be given access to particular service accounts as required.

### Possible Impact
Privilege escalation, impersonation of any/all services

### Suggested Resolution
Provide access at the service-level instead of folder-level, if required


### Insecure Example

The following example will fail the google-iam-no-folder-level-service-account-impersonation check.

{% highlight terraform %}

resource "google_folder_iam_binding" "folder-123" {
	folder = "folder-123"
	role    = "roles/iam.serviceAccountUser"
}

{% endhighlight %}



### Secure Example

The following example will pass the google-iam-no-folder-level-service-account-impersonation check.

{% highlight terraform %}

resource "google_folder_iam_binding" "folder-123" {
	folder = "folder-123"
	role    = "roles/nothingInParticular"
}
			
{% endhighlight %}



### Related Links


- [https://registry.terraform.io/providers/hashicorp/google/latest/docs/resources/google_folder_iam](https://registry.terraform.io/providers/hashicorp/google/latest/docs/resources/google_folder_iam){:target="_blank" rel="nofollow noreferrer noopener"}

- [https://cloud.google.com/iam/docs/impersonating-service-accounts](https://cloud.google.com/iam/docs/impersonating-service-accounts){:target="_blank" rel="nofollow noreferrer noopener"}


