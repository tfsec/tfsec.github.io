---
title: Ensure that logging of disconnections is enabled.
shortcode: google-sql-pg-log-disconnections
legacy: 
summary: Ensure that logging of disconnections is enabled. 
resources: [google_sql_database_instance] 
permalink: /docs/google/sql/pg-log-disconnections/
redirect_from: 
  - /docs/google//
---

### Explanation

Logging disconnections provides useful diagnostic data such as session length, which can identify performance issues in an application and potential DoS vectors.

### Possible Impact
Insufficient diagnostic data.

### Suggested Resolution
Enable disconnection logging.


### Insecure Example

The following example will fail the google-sql-pg-log-disconnections check.

{% highlight terraform %}

resource "google_sql_database_instance" "db" {
	name             = "db"
	database_version = "POSTGRES_12"
	region           = "us-central1"
	settings {
		database_flags {
			name  = "log_disconnections"
			value = "off"
		}
	}
}
			
{% endhighlight %}



### Secure Example

The following example will pass the google-sql-pg-log-disconnections check.

{% highlight terraform %}

resource "google_sql_database_instance" "db" {
	name             = "db"
	database_version = "POSTGRES_12"
	region           = "us-central1"
	settings {
		database_flags {
			name  = "log_disconnections"
			value = "on"
		}
	}
}
			
{% endhighlight %}



### Related Links


- [https://registry.terraform.io/providers/hashicorp/google/latest/docs/resources/sql_database_instance](https://registry.terraform.io/providers/hashicorp/google/latest/docs/resources/sql_database_instance){:target="_blank" rel="nofollow noreferrer noopener"}

- [https://www.postgresql.org/docs/13/runtime-config-logging.html#GUC-LOG-DISCONNECTIONS](https://www.postgresql.org/docs/13/runtime-config-logging.html#GUC-LOG-DISCONNECTIONS){:target="_blank" rel="nofollow noreferrer noopener"}


