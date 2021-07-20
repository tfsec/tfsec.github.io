---
title: Shielded GKE nodes not enabled.
shortcode: google-gke-node-shielding-enabled
legacy: GCP010
summary: Shielded GKE nodes not enabled. 
resources: [google_container_cluster] 
permalink: /docs/google/gke/node-shielding-enabled/
redirect_from: 
  - /docs/google/GCP010/
---

### Explanation


CIS GKE Benchmark Recommendation: 6.5.5. Ensure Shielded GKE Nodes are Enabled

Shielded GKE Nodes provide strong, verifiable node identity and integrity to increase the security of GKE nodes and should be enabled on all GKE clusters.


### Possible Impact
Node identity and integrity can't be verified without shielded GKE nodes

### Suggested Resolution
Enable node shielding


### Insecure Example

The following example will fail the google-gke-node-shielding-enabled check.

{% highlight terraform %}

resource "google_container_cluster" "bad_example" {
	enable_shielded_nodes = "false"
}
{% endhighlight %}



### Secure Example

The following example will pass the google-gke-node-shielding-enabled check.

{% highlight terraform %}

resource "google_container_cluster" "good_example" {
	enable_shielded_nodes = "true"
}
{% endhighlight %}



### Related Links


- [https://cloud.google.com/kubernetes-engine/docs/how-to/hardening-your-cluster#shielded_nodes](https://cloud.google.com/kubernetes-engine/docs/how-to/hardening-your-cluster#shielded_nodes){:target="_blank" rel="nofollow noreferrer noopener"}

- [https://www.terraform.io/docs/providers/google/r/container_cluster.html#enable_shielded_nodes](https://www.terraform.io/docs/providers/google/r/container_cluster.html#enable_shielded_nodes){:target="_blank" rel="nofollow noreferrer noopener"}


