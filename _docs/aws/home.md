---
permalink: /docs/aws/home/
---

The included AWS checks are listed below. For more information about each check, see the link provided.

| Code  | Summary | Details |
|:-------|:-------------|:----------|
|AWS001|S3 Bucket has an ACL defined which allows public access.|[AWS001](/docs/aws/AWS001)|
|AWS002|S3 Bucket does not have logging enabled.|[AWS002](/docs/aws/AWS002)|
|AWS003|AWS Classic resource usage.|[AWS003](/docs/aws/AWS003)|
|AWS004|Use of plain HTTP.|[AWS004](/docs/aws/AWS004)|
|AWS005|Load balancer is exposed to the internet.|[AWS005](/docs/aws/AWS005)|
|AWS006|An ingress security group rule allows traffic from `/0`.|[AWS006](/docs/aws/AWS006)|
|AWS007|An egress security group rule allows traffic to `/0`.|[AWS007](/docs/aws/AWS007)|
|AWS008|An inline ingress security group rule allows traffic from `/0`.|[AWS008](/docs/aws/AWS008)|
|AWS009|An inline egress security group rule allows traffic to `/0`.|[AWS009](/docs/aws/AWS009)|
|AWS010|An outdated SSL policy is in use by a load balancer.|[AWS010](/docs/aws/AWS010)|
|AWS011|A resource is marked as publicly accessible.|[AWS011](/docs/aws/AWS011)|
|AWS012|A resource has a public IP address.|[AWS012](/docs/aws/AWS012)|
|AWS013|Task definition defines sensitive environment variable(s).|[AWS013](/docs/aws/AWS013)|
|AWS014|Launch configuration with unencrypted block device.|[AWS014](/docs/aws/AWS014)|
|AWS015|Unencrypted SQS queue.|[AWS015](/docs/aws/AWS015)|
|AWS016|Unencrypted SNS topic.|[AWS016](/docs/aws/AWS016)|
|AWS017|Unencrypted S3 bucket.|[AWS017](/docs/aws/AWS017)|
|AWS018|Missing description for security group/security group rule.|[AWS018](/docs/aws/AWS018)|
|AWS019|A KMS key is not configured to auto-rotate.|[AWS019](/docs/aws/AWS019)|
|AWS020|CloudFront distribution allows unencrypted (HTTP) communications.|[AWS020](/docs/aws/AWS020)|
|AWS021|CloudFront distribution uses outdated SSL/TSL protocols.|[AWS021](/docs/aws/AWS021)|
|AWS022|A MSK cluster allows unencrypted data in transit.|[AWS022](/docs/aws/AWS022)|
|AWS023|ECR repository has image scans disabled.|[AWS023](/docs/aws/AWS023)|
|AWS024|Kinesis stream is unencrypted.|[AWS024](/docs/aws/AWS024)|
|AWS025|API Gateway domain name uses outdated SSL/TLS protocols.|[AWS025](/docs/aws/AWS025)|
|AWS031|Elasticsearch domain isn't encrypted at rest.|[AWS031](/docs/aws/AWS031)|
|AWS032|Elasticsearch domain uses plaintext traffic for node to node communication.|[AWS032](/docs/aws/AWS032)|
|AWS033|Elasticsearch doesn't enforce HTTPS traffic.|[AWS033](/docs/aws/AWS033)|
|AWS034|Elasticsearch domain endpoint is using outdated TLS policy.|[AWS034](/docs/aws/AWS034)|
|AWS035|Unencrypted Elasticache Replication Group.|[AWS035](/docs/aws/AWS035)|
|AWS036|Elasticache Replication Group uses unencrypted traffic.|[AWS036](/docs/aws/AWS036)|
|AWS037|IAM Password policy should prevent password reuse.|[AWS037](/docs/aws/AWS037)|
|AWS038|IAM Password policy should have expiry less than or equal to 90 days.|[AWS038](/docs/aws/AWS038)|
|AWS039|IAM Password policy should have minimum password length of 14 or more characters.|[AWS039](/docs/aws/AWS039)|
|AWS040|IAM Password policy should have requirement for at least one symbol in the password.|[AWS040](/docs/aws/AWS040)|
|AWS041|IAM Password policy should have requirement for at least one number in the password.|[AWS041](/docs/aws/AWS041)|
|AWS042|IAM Password policy should have requirement for at least one lowercase character.|[AWS042](/docs/aws/AWS042)|
|AWS043|IAM Password policy should have requirement for at least one uppercase character.|[AWS043](/docs/aws/AWS043)|
|AWS044|AWS provider has access credentials specified.|[AWS044](/docs/aws/AWS044)|
|AWS045|CloudFront distribution does not have a WAF in front.|[AWS045](/docs/aws/AWS045)|
|AWS046|AWS IAM policy document has wildcard action statement.|[AWS046](/docs/aws/AWS046)|
|AWS047|AWS SQS policy document has wildcard action statement.|[AWS047](/docs/aws/AWS047)|

