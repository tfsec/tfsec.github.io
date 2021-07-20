---
title: google-storage-enable-ubla - Ensure that Cloud Storage buckets have uniform bucket-level access enabled
summary: Ensure that Cloud Storage buckets have uniform bucket-level access enabled 
resources: [google_storage_bucket] 
permalink: /docs/google/google-storage-enable-ubla/
---
### Explanation

When you enable uniform bucket-level access on a bucket, Access Control Lists (ACLs) are disabled, and only bucket-level Identity and Access Management (IAM) permissions grant access to that bucket and the objects it contains. You revoke all access granted by object ACLs and the ability to administrate permissions using bucket ACLs.

### Possible Impact
ACLs are difficult to manage and often lead to incorrect/unintended configurations.

### Suggested Resolution
Enable uniform bucket level access to provide a uniform permissioning system.


### Insecure Example

The following example will fail the google-storage-enable-ubla check.

{% highlight terraform %}

resource "google_storage_bucket" "static-site" {
	name          = "image-store.com"
	location      = "EU"
	force_destroy = true
	
	uniform_bucket_level_access = false
	
	website {
		main_page_suffix = "index.html"
		not_found_page   = "404.html"
	}
	cors {
		origin          = ["http://image-store.com"]
		method          = ["GET", "HEAD", "PUT", "POST", "DELETE"]
		response_header = ["*"]
		max_age_seconds = 3600
	}
}

{% endhighlight %}



### Secure Example

The following example will pass the google-storage-enable-ubla check.

{% highlight terraform %}

resource "google_storage_bucket" "static-site" {
	name          = "image-store.com"
	location      = "EU"
	force_destroy = true
	
	uniform_bucket_level_access = true
	
	website {
		main_page_suffix = "index.html"
		not_found_page   = "404.html"
	}
	cors {
		origin          = ["http://image-store.com"]
		method          = ["GET", "HEAD", "PUT", "POST", "DELETE"]
		response_header = ["*"]
		max_age_seconds = 3600
	}
}

{% endhighlight %}



### Related Links


- [https://cloud.google.com/storage/docs/uniform-bucket-level-access](https://cloud.google.com/storage/docs/uniform-bucket-level-access){:target="_blank" rel="nofollow noreferrer noopener"}


