---
title: google-compute-enable-shielded-vm
description: Instances should have Shielded VM enabled
shortcode: google-compute-enable-shielded-vm
legacy: 
summary: Instances should have Shielded VM enabled 
resources: [google_compute_instance] 
permalink: /docs/google/compute/enable-shielded-vm/
redirect_from: 
  - /docs/google//
---

### Explanation

A Shielded VM is a VM with enhanced defences/detection for rootkits/bootkits.

### Possible Impact
Unable to detect rootkits

### Suggested Resolution
Enable Shielded VM


### Insecure Example

The following example will fail the google-compute-enable-shielded-vm check.

{% highlight terraform %}

resource "google_compute_instance" "bad_example" {
  name         = "test"
  machine_type = "e2-medium"
  zone         = "us-central1-a"

  tags = ["foo", "bar"]

  boot_disk {
    initialize_params {
      image = "debian-cloud/debian-9"
    }
  }

  // Local SSD disk
  scratch_disk {
    interface = "SCSI"
  }

  shielded_instance_config {
    enable_vtpm = false
    enable_integrity_monitoring = false
  }
}

{% endhighlight %}



### Secure Example

The following example will pass the google-compute-enable-shielded-vm check.

{% highlight terraform %}

resource "google_compute_instance" "bad_example" {
  name         = "test"
  machine_type = "e2-medium"
  zone         = "us-central1-a"

  tags = ["foo", "bar"]

  boot_disk {
    initialize_params {
      image = "debian-cloud/debian-9"
    }
  }

  // Local SSD disk
  scratch_disk {
    interface = "SCSI"
  }

  shielded_instance_config {
    enable_vtpm = true
    enable_integrity_monitoring = true
  }
}

{% endhighlight %}



### Related Links


- [https://registry.terraform.io/providers/hashicorp/google/latest/docs/resources/compute_instance#enable_vtpm](https://registry.terraform.io/providers/hashicorp/google/latest/docs/resources/compute_instance#enable_vtpm){:target="_blank" rel="nofollow noreferrer noopener"}


