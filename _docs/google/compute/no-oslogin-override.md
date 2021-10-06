---
title: Instances should not override the project setting for OS Login
shortcode: google-compute-no-oslogin-override
legacy: 
summary: Instances should not override the project setting for OS Login 
resources: [google_compute_instance] 
permalink: /docs/google/compute/no-oslogin-override/
redirect_from: 
  - /docs/google//
---

### Explanation

OS Login automatically revokes the relevant SSH keys when an IAM user has their access revoked.

### Possible Impact
Access via SSH key cannot be revoked automatically when an IAM user is removed.

### Suggested Resolution
Enable OS Login at project level and remove instance-level overrides


### Insecure Example

The following example will fail the google-compute-no-oslogin-override check.

{% highlight terraform %}

resource "google_compute_instance" "default" {
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

  metadata = {
    enable-oslogin = false
  }
}

{% endhighlight %}



### Secure Example

The following example will pass the google-compute-no-oslogin-override check.

{% highlight terraform %}

resource "google_compute_instance" "default" {
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

  metadata = {
  }
}

{% endhighlight %}



### Related Links


- [https://registry.terraform.io/providers/hashicorp/google/latest/docs/resources/compute_instance#](https://registry.terraform.io/providers/hashicorp/google/latest/docs/resources/compute_instance#){:target="_blank" rel="nofollow noreferrer noopener"}


