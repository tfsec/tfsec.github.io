---
title: aws-iam-require-lowercase-in-passwords - IAM Password policy should have requirement for at least one lowercase character.
summary: IAM Password policy should have requirement for at least one lowercase character. 
resources: [aws_iam_account_password_policy] 
permalink: /docs/aws/aws-iam-require-lowercase-in-passwords/
---
### Explanation

IAM account password policies should ensure that passwords content including at least one lowercase character.

### Possible Impact
Short, simple passwords are easier to compromise

### Suggested Resolution
Enforce longer, more complex passwords in the policy


### Insecure Example

The following example will fail the aws-iam-require-lowercase-in-passwords check.

{% highlight terraform %}

resource "aws_iam_account_password_policy" "bad_example" {
	# ...
	# require_lowercase_characters not set
	# ...
}
{% endhighlight %}



### Secure Example

The following example will pass the aws-iam-require-lowercase-in-passwords check.

{% highlight terraform %}

resource "aws_iam_account_password_policy" "good_example" {
	# ...
	require_lowercase_characters = true
	# ...
}
{% endhighlight %}



### Related Links


- [https://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_passwords_account-policy.html#password-policy-details](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_passwords_account-policy.html#password-policy-details){:target="_blank" rel="nofollow noreferrer noopener"}

- [https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/iam_account_password_policy](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/iam_account_password_policy){:target="_blank" rel="nofollow noreferrer noopener"}


