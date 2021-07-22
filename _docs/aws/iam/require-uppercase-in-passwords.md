---
title: IAM Password policy should have requirement for at least one uppercase character.
shortcode: aws-iam-require-uppercase-in-passwords
legacy: AWS043
summary: IAM Password policy should have requirement for at least one uppercase character. 
resources: [aws_iam_account_password_policy] 
permalink: /docs/aws/iam/require-uppercase-in-passwords/
redirect_from: 
  - /docs/aws/AWS043/
---

### Explanation

,
IAM account password policies should ensure that passwords content including at least one uppercase character.


### Possible Impact
Short, simple passwords are easier to compromise

### Suggested Resolution
Enforce longer, more complex passwords in the policy


### Insecure Example

The following example will fail the aws-iam-require-uppercase-in-passwords check.

{% highlight terraform %}

resource "aws_iam_account_password_policy" "bad_example" {
	# ...
	# require_uppercase_characters not set
	# ...
}

{% endhighlight %}



### Secure Example

The following example will pass the aws-iam-require-uppercase-in-passwords check.

{% highlight terraform %}

resource "aws_iam_account_password_policy" "good_example" {
	# ...
	require_uppercase_characters = true
	# ...
}

{% endhighlight %}



### Related Links


- [https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/iam_account_password_policy](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/iam_account_password_policy){:target="_blank" rel="nofollow noreferrer noopener"}

- [https://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_passwords_account-policy.html#password-policy-details](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_passwords_account-policy.html#password-policy-details){:target="_blank" rel="nofollow noreferrer noopener"}


