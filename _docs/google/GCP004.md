---
title: An outbound firewall rule allows traffic to /0.
shortcode: google-compute-no-public-egress
legacy: GCP004
summary: An outbound firewall rule allows traffic to /0. 
resources: [google_compute_firewall] 
permalink: /docs/google/compute/no-public-egress/
redirect_from: 
  - /docs/google/GCP004/
---

### Explanation


Network security rules should not use very broad subnets.

Where possible, segments should be broken into smaller subnets and avoid using the <code>/0</code> subnet.


### Possible Impact
The port is exposed for egress to the internet

### Suggested Resolution
Set a more restrictive cidr range


### Insecure Example

The following example will fail the google-compute-no-public-egress check.

{% highlight terraform %}

resource "google_compute_firewall" "bad_example" {
	destination_ranges = ["0.0.0.0/0"]
}
{% endhighlight %}



### Secure Example

The following example will pass the google-compute-no-public-egress check.

{% highlight terraform %}

resource "google_compute_firewall" "good_example" {
	destination_ranges = ["1.2.3.4/32"]
}
{% endhighlight %}



### Related Links


- [https://cloud.google.com/vpc/docs/using-firewalls](https://cloud.google.com/vpc/docs/using-firewalls){:target="_blank" rel="nofollow noreferrer noopener"}

- [https://www.terraform.io/docs/providers/google/r/compute_firewall.html](https://www.terraform.io/docs/providers/google/r/compute_firewall.html){:target="_blank" rel="nofollow noreferrer noopener"}


