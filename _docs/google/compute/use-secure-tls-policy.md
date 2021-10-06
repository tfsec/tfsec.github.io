---
title: SSL policies should enforce secure versions of TLS
shortcode: google-compute-use-secure-tls-policy
legacy: 
summary: SSL policies should enforce secure versions of TLS 
resources: [google_compute_ssl_policy] 
permalink: /docs/google/compute/use-secure-tls-policy/
redirect_from: 
  - /docs/google//
---

### Explanation

TLS versions prior to 1.2 are outdated and insecure. You should use 1.2 as aminimum version.

### Possible Impact
Data in transit is not sufficiently secured

### Suggested Resolution
Enforce a minimum TLS version of 1.2


### Insecure Example

The following example will fail the google-compute-use-secure-tls-policy check.

{% highlight terraform %}

resource "google_compute_ssl_policy" "bad_example" {
  name    = "production-ssl-policy"
  profile = "MODERN"
  min_tls_version = "TLS_1_1"
}


{% endhighlight %}



### Secure Example

The following example will pass the google-compute-use-secure-tls-policy check.

{% highlight terraform %}

resource "google_compute_ssl_policy" "good_example" {
  name    = "production-ssl-policy"
  profile = "MODERN"
  min_tls_version = "TLS_1_2"
}

{% endhighlight %}



### Related Links


- [https://registry.terraform.io/providers/hashicorp/google/latest/docs/resources/compute_ssl_policy#min_tls_version](https://registry.terraform.io/providers/hashicorp/google/latest/docs/resources/compute_ssl_policy#min_tls_version){:target="_blank" rel="nofollow noreferrer noopener"}


