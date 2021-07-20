---
title: Task definition defines sensitive environment variable(s).
shortcode: aws-ecs-no-plaintext-secrets
legacy: AWS013
summary: Task definition defines sensitive environment variable(s). 
resources: [aws_ecs_task_definition] 
permalink: /docs/aws/ecs/no-plaintext-secrets/
redirect_from: 
  - /docs/aws/AWS013/
---

### Explanation


You should not make secrets available to a user in plaintext in any scenario. Secrets can instead be pulled from a secure secret storage system by the service requiring them.  


### Possible Impact
Sensitive data could be exposed in the AWS Management Console

### Suggested Resolution
Use secrets for the task definition


### Insecure Example

The following example will fail the aws-ecs-no-plaintext-secrets check.

{% highlight terraform %}

resource "aws_ecs_task_definition" "bad_example" {
  container_definitions = <<EOF
[
  {
    "name": "my_service",
    "essential": true,
    "memory": 256,
    "environment": [
      { "name": "ENVIRONMENT", "value": "development" },
      { "name": "DATABASE_PASSWORD", "value": "oh no D:"}
    ]
  }
]
EOF

}

{% endhighlight %}



### Secure Example

The following example will pass the aws-ecs-no-plaintext-secrets check.

{% highlight terraform %}

resource "aws_ecs_task_definition" "good_example" {
  container_definitions = <<EOF
[
  {
    "name": "my_service",
    "essential": true,
    "memory": 256,
    "environment": [
      { "name": "ENVIRONMENT", "value": "development" }
    ]
  }
]
EOF

}

{% endhighlight %}



### Related Links


- [https://docs.aws.amazon.com/systems-manager/latest/userguide/integration-ps-secretsmanager.html](https://docs.aws.amazon.com/systems-manager/latest/userguide/integration-ps-secretsmanager.html){:target="_blank" rel="nofollow noreferrer noopener"}

- [https://www.vaultproject.io/](https://www.vaultproject.io/){:target="_blank" rel="nofollow noreferrer noopener"}


