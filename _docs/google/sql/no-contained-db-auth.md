---
title: Contained database authentication should be disabled
shortcode: google-sql-no-contained-db-auth
legacy: 
summary: Contained database authentication should be disabled 
resources: [google_sql_database_instance] 
permalink: /docs/google/sql/no-contained-db-auth/
redirect_from: 
  - /docs/google//
---

### Explanation

Users with ALTER permissions on users can grant access to a contained database without the knowledge of an administrator

### Possible Impact
Access can be granted without knowledge of the database administrator

### Suggested Resolution
Disable contained database authentication


### Insecure Example

The following example will fail the google-sql-no-contained-db-auth check.

{% highlight terraform %}

resource "google_sql_database_instance" "db" {
	name             = "db"
	database_version = "SQLSERVER_2017_STANDARD"
	region           = "us-central1"
}
			
{% endhighlight %}



### Secure Example

The following example will pass the google-sql-no-contained-db-auth check.

{% highlight terraform %}

resource "google_sql_database_instance" "db" {
	name             = "db"
	database_version = "SQLSERVER_2017_STANDARD"
	region           = "us-central1"
	settings {
	    database_flags {
		    name  = "contained database authentication"
		    value = "off"
		}
	}
}
			
{% endhighlight %}



### Related Links


- [https://registry.terraform.io/providers/hashicorp/google/latest/docs/resources/sql_database_instance](https://registry.terraform.io/providers/hashicorp/google/latest/docs/resources/sql_database_instance){:target="_blank" rel="nofollow noreferrer noopener"}

- [https://docs.microsoft.com/en-us/sql/database-engine/configure-windows/contained-database-authentication-server-configuration-option?view=sql-server-ver15](https://docs.microsoft.com/en-us/sql/database-engine/configure-windows/contained-database-authentication-server-configuration-option?view=sql-server-ver15){:target="_blank" rel="nofollow noreferrer noopener"}


