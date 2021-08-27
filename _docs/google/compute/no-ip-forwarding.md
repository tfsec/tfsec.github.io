---
title: Instances should not have IP forwarding enabled
shortcode: google-compute-no-ip-forwarding
legacy: 
summary: Instances should not have IP forwarding enabled 
resources: [google_compute_instance] 
permalink: /docs/google/compute/no-ip-forwarding/
redirect_from: 
  - /docs/google//
---

### Explanation

Disabling IP forwarding ensuresthe instance can only receive packets addressed to the instance and can only send packets with a source address of the instance.

### Possible Impact
Instance can send/receive packets without the explicit instance address

### Suggested Resolution
Disable IP forwarding


### Insecure Example

The following example will fail the google-compute-no-ip-forwarding check.

{% highlight terraform %}

resource "google_compute_instance" "bad_example" {
  name         = "test"
  machine_type = "e2-medium"
  zone         = "us-central1-a"

  boot_disk {
    initialize_params {
      image = "debian-cloud/debian-9"
    }
  }

  // Local SSD disk
  scratch_disk {
    interface = "SCSI"
  }

  can_ip_forward = true
}

{% endhighlight %}



### Secure Example

The following example will pass the google-compute-no-ip-forwarding check.

{% highlight terraform %}

resource "google_compute_instance" "bad_example" {
  name         = "test"
  machine_type = "e2-medium"
  zone         = "us-central1-a"

  boot_disk {
    initialize_params {
      image = "debian-cloud/debian-9"
    }
  }

  // Local SSD disk
  scratch_disk {
    interface = "SCSI"
  }
  
  can_ip_forward = false
}

{% endhighlight %}



### Related Links


- [https://registry.terraform.io/providers/hashicorp/google/latest/docs/resources/compute_instance#can_ip_forward](https://registry.terraform.io/providers/hashicorp/google/latest/docs/resources/compute_instance#can_ip_forward){:target="_blank" rel="nofollow noreferrer noopener"}

