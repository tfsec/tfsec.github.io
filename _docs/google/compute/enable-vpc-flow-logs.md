---
title: VPC flow logs should be enabled for all subnets
shortcode: google-compute-enable-vpc-flow-logs
legacy: 
summary: VPC flow logs should be enabled for all subnets 
resources: [google_compute_subnetwork] 
permalink: /docs/google/compute/enable-vpc-flow-logs/
redirect_from: 
  - /docs/google//
---

### Explanation

VPC flow logs record information about all traffic, which is a vital tool in reviewing anomalous traffic.

### Possible Impact
Limited auditing capability and awareness

### Suggested Resolution
Enable VPC flow logs


### Insecure Example

The following example will fail the google-compute-enable-vpc-flow-logs check.

{% highlight terraform %}

resource "google_compute_subnetwork" "bad_example" {
  name          = "test-subnetwork"
  ip_cidr_range = "10.2.0.0/16"
  region        = "us-central1"
  network       = google_compute_network.custom-test.id
  secondary_ip_range {
    range_name    = "tf-test-secondary-range-update1"
    ip_cidr_range = "192.168.10.0/24"
  }
  enable_flow_logs = false
}

resource "google_compute_network" "custom-test" {
  name                    = "test-network"
  auto_create_subnetworks = false
}

{% endhighlight %}



### Secure Example

The following example will pass the google-compute-enable-vpc-flow-logs check.

{% highlight terraform %}

resource "google_compute_subnetwork" "good_example" {
  name          = "test-subnetwork"
  ip_cidr_range = "10.2.0.0/16"
  region        = "us-central1"
  network       = google_compute_network.custom-test.id
  secondary_ip_range {
    range_name    = "tf-test-secondary-range-update1"
    ip_cidr_range = "192.168.10.0/24"
  }
  enable_flow_logs = true
}

resource "google_compute_network" "custom-test" {
  name                    = "test-network"
  auto_create_subnetworks = false
}

{% endhighlight %}



### Related Links


- [https://registry.terraform.io/providers/hashicorp/google/latest/docs/resources/compute_subnetwork#enable_flow_logs](https://registry.terraform.io/providers/hashicorp/google/latest/docs/resources/compute_subnetwork#enable_flow_logs){:target="_blank" rel="nofollow noreferrer noopener"}

