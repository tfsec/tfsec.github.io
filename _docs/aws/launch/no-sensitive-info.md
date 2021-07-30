---
title: Ensure all data stored in the Launch configuration EBS is securely encrypted
shortcode: aws-launch-no-sensitive-info
legacy: 
summary: Ensure all data stored in the Launch configuration EBS is securely encrypted 
resources: [aws_launch_configuration] 
permalink: /docs/aws/launch/no-sensitive-info/
redirect_from: 
  - /docs/aws//
---

### Explanation

When creating Launch Configurations, user data can be used for the initial configuration of the instance. User data must not contain any sensitive data.

### Possible Impact
Sensitive credentials in user data can be leaked

### Suggested Resolution
Don't use sensitive data in user data


### Insecure Example

The following example will fail the aws-launch-no-sensitive-info check.

{% highlight terraform %}

resource "aws_launch_configuration" "as_conf" {
  name          = "web_config"
  image_id      = data.aws_ami.ubuntu.id
  instance_type = "t2.micro"
  user_data     = <<EOF
export DATABASE_PASSWORD=\"SomeSortOfPassword\"
EOF
}

{% endhighlight %}



### Secure Example

The following example will pass the aws-launch-no-sensitive-info check.

{% highlight terraform %}

resource "aws_launch_configuration" "as_conf" {
  name          = "web_config"
  image_id      = data.aws_ami.ubuntu.id
  instance_type = "t2.micro"
  user_data     = <<EOF
export GREETING="Hello there"
EOF
}

{% endhighlight %}



### Related Links


- [https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/launch_configuration#user_data,user_data_base64](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/launch_configuration#user_data,user_data_base64){:target="_blank" rel="nofollow noreferrer noopener"}


