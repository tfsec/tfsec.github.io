---
title: IAM Password policy should have requirement for at least one symbol in the password.
shortcode: aws-iam-require-symbols-in-passwords
legacy: AWS040
summary: IAM Password policy should have requirement for at least one symbol in the password. 
resources: [aws_iam_account_password_policy] 
permalink: /docs/aws/iam/require-symbols-in-passwords/
redirect_from: 
  - /docs/aws/AWS040/
---

### Explanation

IAM account password policies should ensure that passwords content including a symbol.

### Possible Impact
Short, simple passwords are easier to compromise

### Suggested Resolution
Enforce longer, more complex passwords in the policy


### Insecure Example

The following example will fail the aws-iam-require-symbols-in-passwords check.

{% highlight terraform %}

resource "aws_iam_account_password_policy" "bad_example" {
	# ...
	# require_symbols not set
	# ...
}

{% endhighlight %}



### Secure Example

The following example will pass the aws-iam-require-symbols-in-passwords check.

{% highlight terraform %}

resource "aws_iam_account_password_policy" "good_example" {
	# ...
	require_symbols = true
	# ...
}

{% endhighlight %}



### Related Links


- [https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/iam_account_password_policy](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/iam_account_password_policy){:target="_blank" rel="nofollow noreferrer noopener"}

- [https://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_passwords_account-policy.html#password-policy-details](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_passwords_account-policy.html#password-policy-details){:target="_blank" rel="nofollow noreferrer noopener"}


