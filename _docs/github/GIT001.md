---
title: github-repositories-private - Github repository shouldn't be public.
summary: Github repository shouldn't be public. 
resources: [github_repository] 
permalink: /docs/github/github-repositories-private/
---
### Explanation


Github repository should be set to be private.

You can do this by either setting <code>private</code> attribute to 'true' or <code>visibility</code> attribute to 'internal' or 'private'.


### Possible Impact
Anyone can read the contents of the GitHub repository and leak IP

### Suggested Resolution
Make sensitive or commercially important repositories private


### Insecure Example

The following example will fail the github-repositories-private check.

{% highlight terraform %}

resource "github_repository" "bad_example" {
  name        = "example"
  description = "My awesome codebase"

  visibility  = "public"

  template {
    owner = "github"
    repository = "terraform-module-template"
  }
}

{% endhighlight %}



### Secure Example

The following example will pass the github-repositories-private check.

{% highlight terraform %}

resource "github_repository" "good_example" {
  name        = "example"
  description = "My awesome codebase"

  visibility  = "private"

  template {
    owner = "github"
    repository = "terraform-module-template"
  }
}

{% endhighlight %}



### Related Links


- [https://docs.github.com/en/github/creating-cloning-and-archiving-repositories/about-repository-visibility](https://docs.github.com/en/github/creating-cloning-and-archiving-repositories/about-repository-visibility){:target="_blank" rel="nofollow noreferrer noopener"}

- [https://docs.github.com/en/github/creating-cloning-and-archiving-repositories/about-repository-visibility#about-internal-repositories](https://docs.github.com/en/github/creating-cloning-and-archiving-repositories/about-repository-visibility#about-internal-repositories){:target="_blank" rel="nofollow noreferrer noopener"}

- [https://registry.terraform.io/providers/integrations/github/latest/docs/resources/repository](https://registry.terraform.io/providers/integrations/github/latest/docs/resources/repository){:target="_blank" rel="nofollow noreferrer noopener"}


