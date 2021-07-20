---
title: google-gke-node-metadata-security - Node metadata value disables metadata concealment.
summary: Node metadata value disables metadata concealment. 
resources: [google_container_cluster google_container_node_pool] 
permalink: /docs/google/google-gke-node-metadata-security/
---
### Explanation


If the <code>workload_metadata_config</code> block within <code>node_config</code> is included, the <code>node_metadata</code> attribute should be configured securely.

The attribute should be set to <code>SECURE</code> to use metadata concealment, or <code>GKE_METADATA_SERVER</code> if workload identity is enabled. This ensures that the VM metadata is not unnecessarily exposed to pods.



### Possible Impact
Metadata that isn't concealed potentially risks leakage of sensitive data

### Suggested Resolution
Set node metadata to SECURE or GKE_METADATA_SERVER


### Insecure Example

The following example will fail the google-gke-node-metadata-security check.

{% highlight terraform %}

resource "google_container_node_pool" "bad_example" {
	node_config {
		workload_metadata_config {
			node_metadata = "EXPOSE"
		}
	}
}
{% endhighlight %}



### Secure Example

The following example will pass the google-gke-node-metadata-security check.

{% highlight terraform %}

resource "google_container_node_pool" "good_example" {
	node_config {
		workload_metadata_config {
			node_metadata = "SECURE"
		}
	}
}
{% endhighlight %}



### Related Links


- [https://cloud.google.com/kubernetes-engine/docs/how-to/protecting-cluster-metadata#create-concealed](https://cloud.google.com/kubernetes-engine/docs/how-to/protecting-cluster-metadata#create-concealed){:target="_blank" rel="nofollow noreferrer noopener"}

- [https://www.terraform.io/docs/providers/google/r/container_cluster.html#node_metadata](https://www.terraform.io/docs/providers/google/r/container_cluster.html#node_metadata){:target="_blank" rel="nofollow noreferrer noopener"}


