---
title: Ensure that logging of lock waits is enabled.
shortcode: google-sql-pg-log-lock-waits
legacy: 
summary: Ensure that logging of lock waits is enabled. 
resources: [google_sql_database_instance] 
permalink: /docs/google/sql/pg-log-lock-waits/
redirect_from: 
  - /docs/google//
---

### Explanation

Lock waits are often an indication of poor performance and often an indicator of a potential denial of service vulnerability, therefore occurrences should be logged for analysis.

### Possible Impact
Issues leading to denial of service may not be identified.

### Suggested Resolution
Enable lock wait logging.


### Insecure Example

The following example will fail the google-sql-pg-log-lock-waits check.

{% highlight terraform %}

resource "google_sql_database_instance" "db" {
	name             = "db"
	database_version = "POSTGRES_12"
	region           = "us-central1"
	settings {
		database_flags {
			name  = "log_lock_waits"
			value = "off"
		}
	}
}
			
{% endhighlight %}



### Secure Example

The following example will pass the google-sql-pg-log-lock-waits check.

{% highlight terraform %}

resource "google_sql_database_instance" "db" {
	name             = "db"
	database_version = "POSTGRES_12"
	region           = "us-central1"
	settings {
		database_flags {
			name  = "log_lock_waits"
			value = "on"
		}
	}
}
			
{% endhighlight %}



### Related Links


- [https://registry.terraform.io/providers/hashicorp/google/latest/docs/resources/sql_database_instance](https://registry.terraform.io/providers/hashicorp/google/latest/docs/resources/sql_database_instance){:target="_blank" rel="nofollow noreferrer noopener"}

- [https://www.postgresql.org/docs/13/runtime-config-logging.html#GUC-LOG-LOCK-WAITS](https://www.postgresql.org/docs/13/runtime-config-logging.html#GUC-LOG-LOCK-WAITS){:target="_blank" rel="nofollow noreferrer noopener"}


