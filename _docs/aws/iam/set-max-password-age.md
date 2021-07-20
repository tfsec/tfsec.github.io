---
title: IAM Password policy should have expiry less than or equal to 90 days.
shortcode: aws-iam-set-max-password-age
legacy: AWS038
summary: IAM Password policy should have expiry less than or equal to 90 days. 
resources: [aws_iam_account_password_policy] 
permalink: /docs/aws/iam/set-max-password-age/
redirect_from: 
  - /docs/aws/AWS038/
---

### Explanation

IAM account password policies should have a maximum age specified. 
		
The account password policy should be set to expire passwords after 90 days or less.

### Possible Impact
Long life password increase the likelihood of a password eventually being compromised

### Suggested Resolution
Limit the password duration with an expiry in the policy


### Insecure Example

The following example will fail the aws-iam-set-max-password-age check.

{% highlight terraform %}

resource "aws_iam_account_password_policy" "bad_example" {
	# ...
	# max_password_age not set
	# ...
}
{% endhighlight %}



### Secure Example

The following example will pass the aws-iam-set-max-password-age check.

{% highlight terraform %}

resource "aws_iam_account_password_policy" "good_example" {
	# ...
	max_password_age = 90
	# ...
}
{% endhighlight %}



### Related Links


- [https://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_passwords_account-policy.html#password-policy-details](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_passwords_account-policy.html#password-policy-details){:target="_blank" rel="nofollow noreferrer noopener"}

- [https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/iam_account_password_policy](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/iam_account_password_policy){:target="_blank" rel="nofollow noreferrer noopener"}


