---
title: google-compute-project-level-oslogin
description: OS Login should be enabled at project level
shortcode: google-compute-project-level-oslogin
legacy: 
summary: OS Login should be enabled at project level 
resources: [google_compute_project_metadata] 
permalink: /docs/google/compute/project-level-oslogin/
redirect_from: 
  - /docs/google//
---

### Explanation

OS Login automatically revokes the relevant SSH keys when an IAM user has their access revoked.

### Possible Impact
Access via SSH key cannot be revoked automatically when an IAM user is removed.

### Suggested Resolution
Enable OS Login at project level


### Insecure Example

The following example will fail the google-compute-project-level-oslogin check.

{% highlight terraform %}

resource "google_compute_project_metadata" "default" {
  metadata = {
	enable-oslogin = false
  }
}

{% endhighlight %}



### Secure Example

The following example will pass the google-compute-project-level-oslogin check.

{% highlight terraform %}

resource "google_compute_project_metadata" "default" {
  metadata = {
    enable-oslogin = true
  }
}

{% endhighlight %}



### Related Links


- [https://registry.terraform.io/providers/hashicorp/google/latest/docs/resources/compute_project_metadata#](https://registry.terraform.io/providers/hashicorp/google/latest/docs/resources/compute_project_metadata#){:target="_blank" rel="nofollow noreferrer noopener"}


