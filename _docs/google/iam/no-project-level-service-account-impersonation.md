---
title: Users should not be granted service account access at the project level
shortcode: google-iam-no-project-level-service-account-impersonation
legacy: 
summary: Users should not be granted service account access at the project level 
resources: [google_project_iam_binding google_project_iam_member] 
permalink: /docs/google/iam/no-project-level-service-account-impersonation/
redirect_from: 
  - /docs/google//
---

### Explanation

Users with service account access at project level can impersonate any service account. Instead, they should be given access to particular service accounts as required.

### Possible Impact
Privilege escalation, impersonation of any/all services

### Suggested Resolution
Provide access at the service-level instead of project-level, if required


### Insecure Example

The following example will fail the google-iam-no-project-level-service-account-impersonation check.

{% highlight terraform %}

resource "google_project_iam_binding" "project-123" {
	project = "project-123"
	role    = "roles/iam.serviceAccountUser"
}

{% endhighlight %}



### Secure Example

The following example will pass the google-iam-no-project-level-service-account-impersonation check.

{% highlight terraform %}

resource "google_project_iam_binding" "project-123" {
	project = "project-123"
	role    = "roles/nothingInParticular"
}
			
{% endhighlight %}



### Related Links


- [https://registry.terraform.io/providers/hashicorp/google/latest/docs/resources/google_project_iam](https://registry.terraform.io/providers/hashicorp/google/latest/docs/resources/google_project_iam){:target="_blank" rel="nofollow noreferrer noopener"}

- [https://cloud.google.com/iam/docs/impersonating-service-accounts](https://cloud.google.com/iam/docs/impersonating-service-accounts){:target="_blank" rel="nofollow noreferrer noopener"}

