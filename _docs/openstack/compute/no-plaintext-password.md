---
title: openstack-compute-no-plaintext-password
description: No plaintext password for compute instance
shortcode: openstack-compute-no-plaintext-password
legacy: 
summary: No plaintext password for compute instance 
resources: [openstack_compute_instance_v2] 
permalink: /docs/openstack/compute/no-plaintext-password/
redirect_from: 
  - /docs/openstack//
---

### Explanation

Assigning a password to the compute instance using plaintext could lead to compromise; it would be preferable to use key-pairs as a login mechanism

### Possible Impact
Including a plaintext password could lead to compromised instance

### Suggested Resolution
Do not use plaintext passwords in terraform files


### Insecure Example

The following example will fail the openstack-compute-no-plaintext-password check.

{% highlight terraform %}

resource "openstack_compute_instance_v2" "bad_example" {
  name            = "basic"
  image_id        = "ad091b52-742f-469e-8f3c-fd81cadf0743"
  flavor_id       = "3"
  admin_pass      = "N0tSoS3cretP4ssw0rd"
  security_groups = ["default"]
  user_data       = "#cloud-config\nhostname: instance_1.example.com\nfqdn: instance_1.example.com"

  network {
    name = "my_network"
  }
}
{% endhighlight %}



### Secure Example

The following example will pass the openstack-compute-no-plaintext-password check.

{% highlight terraform %}

resource "openstack_compute_instance_v2" "good_example" {
  name            = "basic"
  image_id        = "ad091b52-742f-469e-8f3c-fd81cadf0743"
  flavor_id       = "3"
  key_pair        = "my_key_pair_name"
  security_groups = ["default"]
  user_data       = "#cloud-config\nhostname: instance_1.example.com\nfqdn: instance_1.example.com"

  network {
    name = "my_network"
  }
}
{% endhighlight %}



### Related Links


- [https://registry.terraform.io/providers/terraform-provider-openstack/openstack/latest/docs/resources/compute_instance_v2#admin_pass](https://registry.terraform.io/providers/terraform-provider-openstack/openstack/latest/docs/resources/compute_instance_v2#admin_pass){:target="_blank" rel="nofollow noreferrer noopener"}


