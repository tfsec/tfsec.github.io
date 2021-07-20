---
title: IAM policy should avoid use of wildcards and instead apply the principle of least privilege
shortcode: aws-iam-no-policy-wildcards
legacy: AWS099
summary: IAM policy should avoid use of wildcards and instead apply the principle of least privilege 
resources: [aws_iam_policy aws_iam_user_policy aws_iam_group_policy aws_iam_role_policy] 
permalink: /docs/aws/iam/no-policy-wildcards/
redirect_from: 
  - /docs/aws/AWS099/
---

### Explanation


You should use the principle of least privilege when defining your IAM policies. This means you should specify each exact permission required without using wildcards, as this could cause the granting of access to certain undesired actions, resources and principals.


### Possible Impact
Overly permissive policies may grant access to sensitive resources

### Suggested Resolution
Specify the exact permissions required, and to which resources they should apply instead of using wildcards.


### Insecure Example

The following example will fail the aws-iam-no-policy-wildcards check.

{% highlight terraform %}

resource "aws_iam_role_policy" "test_policy" {
	name = "test_policy"
	role = aws_iam_role.test_role.id

	policy = data.aws_iam_policy_document.s3_policy.json
}

resource "aws_iam_role" "test_role" {
	name = "test_role"
	assume_role_policy = jsonencode({
		Version = "2012-10-17"
		Statement = [
		{
			Action = "sts:AssumeRole"
			Effect = "Allow"
			Sid    = ""
			Principal = {
			Service = "s3.amazonaws.com"
			}
		},
		]
	})
}

data "aws_iam_policy_document" "s3_policy" {
  statement {
    principals {
      type        = "AWS"
      identifiers = ["arn:aws:iam::${data.aws_caller_identity.current.account_id}:root"]
    }
    actions   = ["s3:*"]
    resources = ["*"]
  }
}

{% endhighlight %}



### Secure Example

The following example will pass the aws-iam-no-policy-wildcards check.

{% highlight terraform %}

resource "aws_iam_role_policy" "test_policy" {
	name = "test_policy"
	role = aws_iam_role.test_role.id

	policy = data.aws_iam_policy_document.s3_policy.json
}

resource "aws_iam_role" "test_role" {
	name = "test_role"
	assume_role_policy = jsonencode({
		Version = "2012-10-17"
		Statement = [
		{
			Action = "sts:AssumeRole"
			Effect = "Allow"
			Sid    = ""
			Principal = {
			Service = "s3.amazonaws.com"
			}
		},
		]
	})
}

data "aws_iam_policy_document" "s3_policy" {
  statement {
    principals {
      type        = "AWS"
      identifiers = ["arn:aws:iam::${data.aws_caller_identity.current.account_id}:root"]
    }
    actions   = ["s3:GetObject"]
    resources = [aws_s3_bucket.example.arn]
  }
}

{% endhighlight %}



### Related Links


- [https://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html](https://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html){:target="_blank" rel="nofollow noreferrer noopener"}


