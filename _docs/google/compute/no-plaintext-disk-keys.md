---
title: Disk encryption keys should not be provided in plaintext
shortcode: google-compute-no-plaintext-disk-keys
legacy: 
summary: Disk encryption keys should not be provided in plaintext 
resources: [google_compute_disk] 
permalink: /docs/google/compute/no-plaintext-disk-keys/
redirect_from: 
  - /docs/google//
---

### Explanation

Providing your encryption key in plaintext format means anyone with access to the source code also has access to the key.

### Possible Impact
Compromise of encryption keys

### Suggested Resolution
Use managed keys or provide the raw key via a secrets manager 


### Insecure Example

The following example will fail the google-compute-no-plaintext-disk-keys check.

{% highlight terraform %}

resource "google_compute_disk" "bad_example" {
  name  = "test-disk"
  type  = "pd-ssd"
  zone  = "us-central1-a"
  image = "debian-9-stretch-v20200805"
  labels = {
    environment = "dev"
  }
  physical_block_size_bytes = 4096
  disk_encryption_key {
    raw_key = "something"
  }
}

{% endhighlight %}



### Secure Example

The following example will pass the google-compute-no-plaintext-disk-keys check.

{% highlight terraform %}

resource "google_compute_disk" "good_example" {
  name  = "test-disk"
  type  = "pd-ssd"
  zone  = "us-central1-a"
  image = "debian-9-stretch-v20200805"
  labels = {
    environment = "dev"
  }
  physical_block_size_bytes = 4096
}

{% endhighlight %}



### Related Links


- [https://registry.terraform.io/providers/hashicorp/google/latest/docs/resources/compute_disk#raw_key](https://registry.terraform.io/providers/hashicorp/google/latest/docs/resources/compute_disk#raw_key){:target="_blank" rel="nofollow noreferrer noopener"}


