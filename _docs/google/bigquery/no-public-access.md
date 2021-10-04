---
title: google-bigquery-no-public-access
description: BigQuery datasets should only be accessible within the organisation
shortcode: google-bigquery-no-public-access
legacy: 
summary: BigQuery datasets should only be accessible within the organisation 
resources: [google_bigquery_dataset] 
permalink: /docs/google/bigquery/no-public-access/
redirect_from: 
  - /docs/google//
---

### Explanation

Using 'allAuthenticatedUsers' provides any GCP user - even those outside of your organisation - access to your BigQuery dataset.

### Possible Impact
Exposure of sensitive data to the public iniernet

### Suggested Resolution
Configure access permissions with higher granularity


### Insecure Example

The following example will fail the google-bigquery-no-public-access check.

{% highlight terraform %}

resource "google_bigquery_dataset" "bad_example" {
  dataset_id                  = "example_dataset"
  friendly_name               = "test"
  description                 = "This is a test description"
  location                    = "EU"
  default_table_expiration_ms = 3600000

  labels = {
    env = "default"
  }

  access {
    role          = "OWNER"
    special_group = "allAuthenticatedUsers"
  }

  access {
    role   = "READER"
    domain = "hashicorp.com"
  }
}


{% endhighlight %}



### Secure Example

The following example will pass the google-bigquery-no-public-access check.

{% highlight terraform %}

resource "google_bigquery_dataset" "good_example" {
  dataset_id                  = "example_dataset"
  friendly_name               = "test"
  description                 = "This is a test description"
  location                    = "EU"
  default_table_expiration_ms = 3600000

  labels = {
    env = "default"
  }

  access {
    role          = "OWNER"
    user_by_email = google_service_account.bqowner.email
  }

  access {
    role   = "READER"
    domain = "hashicorp.com"
  }
}

resource "google_service_account" "bqowner" {
  account_id = "bqowner"
}

{% endhighlight %}



### Related Links


- [https://registry.terraform.io/providers/hashicorp/google/latest/docs/resources/bigquery_dataset#special_group](https://registry.terraform.io/providers/hashicorp/google/latest/docs/resources/bigquery_dataset#special_group){:target="_blank" rel="nofollow noreferrer noopener"}


