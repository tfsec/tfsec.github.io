---
title: google-gke-use-rbac-permissions - Legacy ABAC permissions are enabled.
summary: Legacy ABAC permissions are enabled. 
resources: [google_container_cluster] 
permalink: /docs/google/google-gke-use-rbac-permissions/
---
### Explanation


You should disable Attribute-Based Access Control (ABAC), and instead use Role-Based Access Control (RBAC) in GKE.

RBAC has significant security advantages and is now stable in Kubernetes, so it’s time to disable ABAC.


### Possible Impact
ABAC permissions are less secure than RBAC permissions

### Suggested Resolution
Switch to using RBAC permissions


### Insecure Example

The following example will fail the google-gke-use-rbac-permissions check.

{% highlight terraform %}

resource "google_container_cluster" "bad_example" {
	enable_legacy_abac = "true"
}

{% endhighlight %}



### Secure Example

The following example will pass the google-gke-use-rbac-permissions check.

{% highlight terraform %}

resource "google_container_cluster" "good_example" {
	# ...
	# enable_legacy_abac not set
	# ...
}

{% endhighlight %}



### Related Links


- [https://cloud.google.com/kubernetes-engine/docs/how-to/hardening-your-cluster#leave_abac_disabled_default_for_110](https://cloud.google.com/kubernetes-engine/docs/how-to/hardening-your-cluster#leave_abac_disabled_default_for_110){:target="_blank" rel="nofollow noreferrer noopener"}

- [https://www.terraform.io/docs/providers/google/r/container_cluster.html#enable_legacy_abac](https://www.terraform.io/docs/providers/google/r/container_cluster.html#enable_legacy_abac){:target="_blank" rel="nofollow noreferrer noopener"}


