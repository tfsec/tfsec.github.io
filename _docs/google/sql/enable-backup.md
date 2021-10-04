---
title: google-sql-enable-backup
description: Enable automated backups to recover from data-loss
shortcode: google-sql-enable-backup
legacy: 
summary: Enable automated backups to recover from data-loss 
resources: [google_sql_database_instance] 
permalink: /docs/google/sql/enable-backup/
redirect_from: 
  - /docs/google//
---

### Explanation

Automated backups are not enabled by default. Backups are an easy way to restore data in a corruption or data-loss scenario.

### Possible Impact
No recovery of lost or corrupted data

### Suggested Resolution
Enable automated backups


### Insecure Example

The following example will fail the google-sql-enable-backup check.

{% highlight terraform %}

resource "google_sql_database_instance" "db" {
	name             = "db"
	database_version = "POSTGRES_12"
	region           = "us-central1"
	settings {
		backup_configuration {
			enabled = false
		}
	}
}
			
{% endhighlight %}



### Secure Example

The following example will pass the google-sql-enable-backup check.

{% highlight terraform %}

resource "google_sql_database_instance" "db" {
	name             = "db"
	database_version = "POSTGRES_12"
	region           = "us-central1"
	settings {
		backup_configuration {
			enabled = true
		}
	}
}
			
{% endhighlight %}



### Related Links


- [https://registry.terraform.io/providers/hashicorp/google/latest/docs/resources/sql_database_instance#settings.backup_configuration.enabled=true](https://registry.terraform.io/providers/hashicorp/google/latest/docs/resources/sql_database_instance#settings.backup_configuration.enabled=true){:target="_blank" rel="nofollow noreferrer noopener"}

- [https://cloud.google.com/sql/docs/mysql/backup-recovery/backups](https://cloud.google.com/sql/docs/mysql/backup-recovery/backups){:target="_blank" rel="nofollow noreferrer noopener"}


