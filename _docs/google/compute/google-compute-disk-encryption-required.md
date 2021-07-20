---
title: google-compute-disk-encryption-required - The encryption key used to encrypt a compute disk has been specified in plaintext.
summary: The encryption key used to encrypt a compute disk has been specified in plaintext. 
resources: [google_compute_disk] 
permalink: /docs/google/google-compute-disk-encryption-required/
---
### Explanation


Sensitive values such as raw encryption keys should not be included in your Terraform code, and should be stored securely by a secrets manager.


### Possible Impact
The encryption key should be considered compromised as it is not stored securely.

### Suggested Resolution
Reference a managed key rather than include the key in raw format.


### Insecure Example

The following example will fail the google-compute-disk-encryption-required check.

{% highlight terraform %}

resource "google_compute_disk" "good_example" {
	disk_encryption_key {
		raw_key="b2ggbm8gdGhpcyBpcyBiYWQ="
	}
}

{% endhighlight %}



### Secure Example

The following example will pass the google-compute-disk-encryption-required check.

{% highlight terraform %}

resource "google_compute_disk" "good_example" {
	disk_encryption_key {
		kms_key_self_link = google_kms_crypto_key.my_crypto_key.id
	}
}

{% endhighlight %}



### Related Links


- [https://registry.terraform.io/providers/hashicorp/google/latest/docs/resources/compute_disk#kms_key_self_link](https://registry.terraform.io/providers/hashicorp/google/latest/docs/resources/compute_disk#kms_key_self_link){:target="_blank" rel="nofollow noreferrer noopener"}

- [https://cloud.google.com/compute/docs/disks/customer-supplied-encryption](https://cloud.google.com/compute/docs/disks/customer-supplied-encryption){:target="_blank" rel="nofollow noreferrer noopener"}


