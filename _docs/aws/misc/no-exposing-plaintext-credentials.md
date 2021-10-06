---
title: AWS provider has access credentials specified.
shortcode: aws-misc-no-exposing-plaintext-credentials
legacy: AWS044
summary: AWS provider has access credentials specified. 
resources: [aws] 
permalink: /docs/aws/misc/no-exposing-plaintext-credentials/
redirect_from: 
  - /docs/aws/AWS044/
---

### Explanation


The AWS provider block should not contain hardcoded credentials. These can be passed in securely as runtime using environment variables.


### Possible Impact
Exposing the credentials in the Terraform provider increases the risk of secret leakage

### Suggested Resolution
Don't include access credentials in plain text


### Insecure Example

The following example will fail the aws-misc-no-exposing-plaintext-credentials check.

{% highlight terraform %}

provider "aws" {
  access_key = "AKIAABCD12ABCDEF1ABC"
  secret_key = "s8d7ghas9dghd9ophgs9"
}

{% endhighlight %}



### Secure Example

The following example will pass the aws-misc-no-exposing-plaintext-credentials check.

{% highlight terraform %}

provider "aws" {
}

{% endhighlight %}



### Related Links


- [https://registry.terraform.io/providers/hashicorp/aws/latest/docs#argument-reference](https://registry.terraform.io/providers/hashicorp/aws/latest/docs#argument-reference){:target="_blank" rel="nofollow noreferrer noopener"}

- [https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-files.html](https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-files.html){:target="_blank" rel="nofollow noreferrer noopener"}


