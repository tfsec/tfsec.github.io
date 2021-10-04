---
title: digitalocean-spaces-disable-force-destroy
description: Force destroy is enabled on Spaces bucket which is dangerous
shortcode: digitalocean-spaces-disable-force-destroy
legacy: DIG007
summary: Force destroy is enabled on Spaces bucket which is dangerous 
resources: [digitalocean_spaces_bucket] 
permalink: /docs/digitalocean/spaces/disable-force-destroy/
redirect_from: 
  - /docs/digitalocean/DIG007/
---

### Explanation


Enabling force destroy on a Spaces bucket means that the bucket can be deleted without the additional check that it is empty. This risks important data being accidentally deleted by a bucket removal process.


### Possible Impact
Accidental deletion of bucket objects

### Suggested Resolution
Don't use force destroy on bucket configuration


### Insecure Example

The following example will fail the digitalocean-spaces-disable-force-destroy check.

{% highlight terraform %}

resource "digitalocean_spaces_bucket" "bad_example" {
  name   		= "foobar"
  region 		= "nyc3"
  force_destroy = true
}

{% endhighlight %}



### Secure Example

The following example will pass the digitalocean-spaces-disable-force-destroy check.

{% highlight terraform %}

resource "digitalocean_spaces_bucket" "good_example" {
  name   = "foobar"
  region = "nyc3"
}

{% endhighlight %}



### Related Links


- [https://registry.terraform.io/providers/digitalocean/digitalocean/latest/docs/resources/spaces_bucket#force_destroy](https://registry.terraform.io/providers/digitalocean/digitalocean/latest/docs/resources/spaces_bucket#force_destroy){:target="_blank" rel="nofollow noreferrer noopener"}


