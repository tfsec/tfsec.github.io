---
title: Disable serial port connectivity for all instances
shortcode: google-compute-no-serial-port
legacy: 
summary: Disable serial port connectivity for all instances 
resources: [google_compute_instance] 
permalink: /docs/google/compute/no-serial-port/
redirect_from: 
  - /docs/google//
---

### Explanation

When serial port access is enabled, the access is not governed by network security rules meaning the port can be exposed publicly.

### Possible Impact
Unrestricted network access to the serial console of the instance

### Suggested Resolution
Disable serial port access


### Insecure Example

The following example will fail the google-compute-no-serial-port check.

{% highlight terraform %}

resource "google_service_account" "default" {
  account_id   = "service_account_id"
  display_name = "Service Account"
}

resource "google_compute_instance" "default" {
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

  network_interface {
    network = "default"

    access_config {
      // Ephemeral IP
    }
  }

  metadata = {
    serial-port-enable = true
  }

  metadata_startup_script = "echo hi > /test.txt"

  service_account {
    # Google recommends custom service accounts that have cloud-platform scope and permissions granted via IAM Roles.
    email  = google_service_account.default.email
    scopes = ["cloud-platform"]
  }
}

{% endhighlight %}



### Secure Example

The following example will pass the google-compute-no-serial-port check.

{% highlight terraform %}

resource "google_service_account" "default" {
  account_id   = "service_account_id"
  display_name = "Service Account"
}

resource "google_compute_instance" "default" {
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

  network_interface {
    network = "default"

    access_config {
      // Ephemeral IP
    }
  }

  metadata = {
    serial-port-enable = false
  }

  metadata_startup_script = "echo hi > /test.txt"

  service_account {
    # Google recommends custom service accounts that have cloud-platform scope and permissions granted via IAM Roles.
    email  = google_service_account.default.email
    scopes = ["cloud-platform"]
  }
}

{% endhighlight %}



### Related Links


- [https://registry.terraform.io/providers/hashicorp/google/latest/docs/resources/compute_instance#](https://registry.terraform.io/providers/hashicorp/google/latest/docs/resources/compute_instance#){:target="_blank" rel="nofollow noreferrer noopener"}

