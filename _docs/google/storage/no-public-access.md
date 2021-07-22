---
title: Ensure that Cloud Storage bucket is not anonymously or publicly accessible.
shortcode: google-storage-no-public-access
legacy: 
summary: Ensure that Cloud Storage bucket is not anonymously or publicly accessible. 
resources: [google_storage_bucket_iam_binding google_storage_bucket_iam_member] 
permalink: /docs/google/storage/no-public-access/
redirect_from: 
  - /docs/google//
---

### Explanation

Using 'allUsers' or 'allAuthenticatedUsers' as members in an IAM member/binding causes data to be exposed outside of the organisation.

### Possible Impact
Public exposure of sensitive data.

### Suggested Resolution
Restrict public access to the bucket.


### Insecure Example

The following example will fail the google-storage-no-public-access check.

{% highlight terraform %}

resource "google_storage_bucket_iam_binding" "binding" {
	bucket = google_storage_bucket.default.name
	role = "roles/storage.admin"
	members = [
		"allAuthenticatedUsers",
	]
}
			
{% endhighlight %}



### Secure Example

The following example will pass the google-storage-no-public-access check.

{% highlight terraform %}

resource "google_storage_bucket_iam_binding" "binding" {
	bucket = google_storage_bucket.default.name
	role = "roles/storage.admin"
	members = [
		"user:jane@example.com",
	]
}
			
{% endhighlight %}



### Related Links


- [https://registry.terraform.io/providers/hashicorp/google/latest/docs/resources/storage_bucket_iam#member/members](https://registry.terraform.io/providers/hashicorp/google/latest/docs/resources/storage_bucket_iam#member/members){:target="_blank" rel="nofollow noreferrer noopener"}

- [https://jbrojbrojbro.medium.com/you-make-the-rules-with-authentication-controls-for-cloud-storage-53c32543747b](https://jbrojbrojbro.medium.com/you-make-the-rules-with-authentication-controls-for-cloud-storage-53c32543747b){:target="_blank" rel="nofollow noreferrer noopener"}


