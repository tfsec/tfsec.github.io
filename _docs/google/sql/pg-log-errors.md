---
title: Ensure that Postgres errors are logged
shortcode: google-sql-pg-log-errors
legacy: 
summary: Ensure that Postgres errors are logged 
resources: [google_sql_database_instance] 
permalink: /docs/google/sql/pg-log-errors/
redirect_from: 
  - /docs/google//
---

### Explanation

Setting the minimum log severity too high will cause errors not to be logged

### Possible Impact
Loss of error logging

### Suggested Resolution
Set the minimum log severity to at least ERROR


### Insecure Example

The following example will fail the google-sql-pg-log-errors check.

{% highlight terraform %}

resource "google_sql_database_instance" "db" {
	name             = "db"
	database_version = "POSTGRES_12"
	region           = "us-central1"
	settings {
		database_flags {
			name  = "log_min_messages"
			value = "PANIC"
		}
	}
}
			
{% endhighlight %}



### Secure Example

The following example will pass the google-sql-pg-log-errors check.

{% highlight terraform %}

resource "google_sql_database_instance" "db" {
	name             = "db"
	database_version = "POSTGRES_12"
	region           = "us-central1"
	settings {
		database_flags {
			name  = "log_min_messages"
			value = "WARNING"
		}
	}
}
			
{% endhighlight %}



### Related Links


- [https://registry.terraform.io/providers/hashicorp/google/latest/docs/resources/sql_database_instance](https://registry.terraform.io/providers/hashicorp/google/latest/docs/resources/sql_database_instance){:target="_blank" rel="nofollow noreferrer noopener"}

- [https://postgresqlco.nf/doc/en/param/log_min_messages/](https://postgresqlco.nf/doc/en/param/log_min_messages/){:target="_blank" rel="nofollow noreferrer noopener"}

- [https://www.postgresql.org/docs/13/runtime-config-logging.html#GUC-LOG-MIN-MESSAGES](https://www.postgresql.org/docs/13/runtime-config-logging.html#GUC-LOG-MIN-MESSAGES){:target="_blank" rel="nofollow noreferrer noopener"}


