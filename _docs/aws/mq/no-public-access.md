---
title: Ensure MQ Broker is not publicly exposed
shortcode: aws-mq-no-public-access
legacy: 
summary: Ensure MQ Broker is not publicly exposed 
resources: [aws_mq_broker] 
permalink: /docs/aws/mq/no-public-access/
redirect_from: 
  - /docs/aws//
---

### Explanation

Public access of the MQ broker should be disabled and only allow routes to applications that require access.

### Possible Impact
Publicly accessible MQ Broker may be vulnerable to compromise

### Suggested Resolution
Disable public access when not required


### Insecure Example

The following example will fail the aws-mq-no-public-access check.

{% highlight terraform %}

resource "aws_mq_broker" "bad_example" {
  broker_name = "example"

  configuration {
    id       = aws_mq_configuration.test.id
    revision = aws_mq_configuration.test.latest_revision
  }

  engine_type        = "ActiveMQ"
  engine_version     = "5.15.0"
  host_instance_type = "mq.t2.micro"
  security_groups    = [aws_security_group.test.id]

  user {
    username = "ExampleUser"
    password = "MindTheGap"
  }
  publicly_accessible = true
}

{% endhighlight %}



### Secure Example

The following example will pass the aws-mq-no-public-access check.

{% highlight terraform %}

resource "aws_mq_broker" "good_example" {
  broker_name = "example"

  configuration {
    id       = aws_mq_configuration.test.id
    revision = aws_mq_configuration.test.latest_revision
  }

  engine_type        = "ActiveMQ"
  engine_version     = "5.15.0"
  host_instance_type = "mq.t2.micro"
  security_groups    = [aws_security_group.test.id]

  user {
    username = "ExampleUser"
    password = "MindTheGap"
  }
  publicly_accessible = false
}

{% endhighlight %}



### Related Links


- [https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/mq_broker#publicly_accessible](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/mq_broker#publicly_accessible){:target="_blank" rel="nofollow noreferrer noopener"}


