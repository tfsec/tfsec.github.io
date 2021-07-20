---
title: IAM Password policy should prevent password reuse.
shortcode: aws-iam-no-password-reuse
legacy: AWS037
summary: IAM Password policy should prevent password reuse. 
resources: [aws_iam_account_password_policy] 
permalink: /docs/aws/iam/no-password-reuse/
redirect_from: 
  - /docs/aws/AWS037/
---

### Explanation


IAM account password policies should prevent the reuse of passwords. 

The account password policy should be set to prevent using any of the last five used passwords.
			

### Possible Impact
Password reuse increase the risk of compromised passwords being abused

### Suggested Resolution
Prevent password reuse in the policy


### Insecure Example

The following example will fail the aws-iam-no-password-reuse check.

{% highlight terraform %}

resource "aws_iam_account_password_policy" "bad_example" {
	# ...
	password_reuse_prevention = 1
	# ...
}
			
{% endhighlight %}



### Secure Example

The following example will pass the aws-iam-no-password-reuse check.

{% highlight terraform %}

resource "aws_iam_account_password_policy" "good_example" {
	# ...
	password_reuse_prevention = 5
	# ...
}
			
{% endhighlight %}



### Related Links


- [https://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_passwords_account-policy.html#password-policy-details](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_passwords_account-policy.html#password-policy-details){:target="_blank" rel="nofollow noreferrer noopener"}

- [https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/iam_account_password_policy](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/iam_account_password_policy){:target="_blank" rel="nofollow noreferrer noopener"}


