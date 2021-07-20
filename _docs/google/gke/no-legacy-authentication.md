---
title: Legacy client authentication methods utilized.
shortcode: google-gke-no-legacy-authentication
legacy: GCP008
summary: Legacy client authentication methods utilized. 
resources: [google_container_cluster] 
permalink: /docs/google/gke/no-legacy-authentication/
redirect_from: 
  - /docs/google/GCP008/
---

### Explanation


It is recommended to use Service Accounts and OAuth as authentication methods for accessing the master in the container cluster. 

Basic authentication should be disabled by explicitly unsetting the <code>username</code> and <code>password</code> on the <code>master_auth</code> block.


### Possible Impact
Username and password authentication methods are less secure

### Suggested Resolution
Use service account or OAuth for authentication


### Insecure Example

The following example will fail the google-gke-no-legacy-authentication check.

{% highlight terraform %}

resource "google_container_cluster" "bad_example" {
}

resource "google_container_cluster" "gke" {
	master_auth {
	    username = ""
	    password = ""
		client_certificate_config {
			issue_client_certificate = true
	    }
	}
}

{% endhighlight %}



### Secure Example

The following example will pass the google-gke-no-legacy-authentication check.

{% highlight terraform %}

resource "google_container_cluster" "good_example" {
	master_auth {
	    username = ""
	    password = ""
	}
}

{% endhighlight %}



### Related Links


- [https://cloud.google.com/kubernetes-engine/docs/how-to/hardening-your-cluster#restrict_authn_methods](https://cloud.google.com/kubernetes-engine/docs/how-to/hardening-your-cluster#restrict_authn_methods){:target="_blank" rel="nofollow noreferrer noopener"}

- [https://www.terraform.io/docs/providers/google/r/container_cluster.html#master_auth](https://www.terraform.io/docs/providers/google/r/container_cluster.html#master_auth){:target="_blank" rel="nofollow noreferrer noopener"}


