---
title: aws-ecs-enable-container-insight - ECS clusters should have container insights enabled
summary: ECS clusters should have container insights enabled 
resources: [aws_ecs_cluster] 
permalink: /docs/aws/aws-ecs-enable-container-insight/
---
### Explanation


Cloudwatch Container Insights provide more metrics and logs for container based applications and micro services.


### Possible Impact
Not all metrics and logs may be gathered for containers when Container Insights isn't enabled

### Suggested Resolution
Enable Container Insights


### Insecure Example

The following example will fail the aws-ecs-enable-container-insight check.

{% highlight terraform %}

resource "aws_ecs_cluster" "bad_example" {
  	name = "services-cluster"
}

{% endhighlight %}



### Secure Example

The following example will pass the aws-ecs-enable-container-insight check.

{% highlight terraform %}

resource "aws_ecs_cluster" "good_example" {
	name = "services-cluster"
  
	setting {
	  name  = "containerInsights"
	  value = "enabled"
	}
}

{% endhighlight %}



### Related Links


- [https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/ecs_cluster#setting](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/ecs_cluster#setting){:target="_blank" rel="nofollow noreferrer noopener"}

- [https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/ContainerInsights.html](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/ContainerInsights.html){:target="_blank" rel="nofollow noreferrer noopener"}

