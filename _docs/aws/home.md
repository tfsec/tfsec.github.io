---
title: AWS Checks
permalink: /docs/aws/home/
has_children: true
has_toc: false
---

The included AWS checks are listed below. For more information about each check, see the link provided.

| ID  | Summary |
|:-------|:-------------|
|[AWS001](/docs/aws/AWS001)|S3 Bucket has an ACL defined which allows public access.|
|[AWS002](/docs/aws/AWS002)|S3 Bucket does not have logging enabled.|
|[AWS003](/docs/aws/AWS003)|AWS Classic resource usage.|
|[AWS004](/docs/aws/AWS004)|Use of plain HTTP.|
|[AWS005](/docs/aws/AWS005)|Load balancer is exposed to the internet.|
|[AWS006](/docs/aws/AWS006)|An ingress security group rule allows traffic from /0.|
|[AWS007](/docs/aws/AWS007)|An egress security group rule allows traffic to /0.|
|[AWS008](/docs/aws/AWS008)|An inline ingress security group rule allows traffic from /0.|
|[AWS009](/docs/aws/AWS009)|An inline egress security group rule allows traffic to /0.|
|[AWS010](/docs/aws/AWS010)|An outdated SSL policy is in use by a load balancer.|
|[AWS011](/docs/aws/AWS011)|A database resource is marked as publicly accessible.|
|[AWS012](/docs/aws/AWS012)|A resource has a public IP address.|
|[AWS013](/docs/aws/AWS013)|Task definition defines sensitive environment variable(s).|
|[AWS014](/docs/aws/AWS014)|Launch configuration with unencrypted block device.|
|[AWS015](/docs/aws/AWS015)|Unencrypted SQS queue.|
|[AWS016](/docs/aws/AWS016)|Unencrypted SNS topic.|
|[AWS017](/docs/aws/AWS017)|Unencrypted S3 bucket.|
|[AWS018](/docs/aws/AWS018)|Missing description for security group/security group rule.|
|[AWS019](/docs/aws/AWS019)|A KMS key is not configured to auto-rotate.|
|[AWS020](/docs/aws/AWS020)|CloudFront distribution allows unencrypted (HTTP) communications.|
|[AWS021](/docs/aws/AWS021)|CloudFront distribution uses outdated SSL/TLS protocols.|
|[AWS022](/docs/aws/AWS022)|A MSK cluster allows unencrypted data in transit.|
|[AWS023](/docs/aws/AWS023)|ECR repository has image scans disabled.|
|[AWS024](/docs/aws/AWS024)|Kinesis stream is unencrypted.|
|[AWS025](/docs/aws/AWS025)|API Gateway domain name uses outdated SSL/TLS protocols.|
|[AWS031](/docs/aws/AWS031)|Elasticsearch domain isn't encrypted at rest.|
|[AWS032](/docs/aws/AWS032)|Elasticsearch domain uses plaintext traffic for node to node communication.|
|[AWS033](/docs/aws/AWS033)|Elasticsearch doesn't enforce HTTPS traffic.|
|[AWS034](/docs/aws/AWS034)|Elasticsearch domain endpoint is using outdated TLS policy.|
|[AWS035](/docs/aws/AWS035)|Unencrypted Elasticache Replication Group.|
|[AWS036](/docs/aws/AWS036)|Elasticache Replication Group uses unencrypted traffic.|
|[AWS037](/docs/aws/AWS037)|IAM Password policy should prevent password reuse.|
|[AWS038](/docs/aws/AWS038)|IAM Password policy should have expiry less than or equal to 90 days.|
|[AWS039](/docs/aws/AWS039)|IAM Password policy should have minimum password length of 14 or more characters.|
|[AWS040](/docs/aws/AWS040)|IAM Password policy should have requirement for at least one symbol in the password.|
|[AWS041](/docs/aws/AWS041)|IAM Password policy should have requirement for at least one number in the password.|
|[AWS042](/docs/aws/AWS042)|IAM Password policy should have requirement for at least one lowercase character.|
|[AWS043](/docs/aws/AWS043)|IAM Password policy should have requirement for at least one uppercase character.|
|[AWS044](/docs/aws/AWS044)|AWS provider has access credentials specified.|
|[AWS045](/docs/aws/AWS045)|CloudFront distribution does not have a WAF in front.|
|[AWS046](/docs/aws/AWS046)|AWS IAM policy document has wildcard action statement.|
|[AWS047](/docs/aws/AWS047)|AWS SQS policy document has wildcard action statement.|
|[AWS048](/docs/aws/AWS048)|EFS Encryption has not been enabled|
|[AWS049](/docs/aws/AWS049)|An ingress Network ACL rule allows specific ports from /0.|
|[AWS050](/docs/aws/AWS050)|An ingress Network ACL rule allows ALL ports from /0.|
|[AWS051](/docs/aws/AWS051)|There is no encryption specified or encryption is disabled on the RDS Cluster.|
|[AWS052](/docs/aws/AWS052)|RDS encryption has not been enabled at a DB Instance level.|
|[AWS053](/docs/aws/AWS053)|Encryption for RDS Performance Insights should be enabled.|
|[AWS057](/docs/aws/AWS057)|Domain logging should be enabled for Elastic Search domains|
|[AWS058](/docs/aws/AWS058)|Ensure that lambda function permission has a source arn specified|
|[AWS059](/docs/aws/AWS059)|Athena databases and workgroup configurations are created unencrypted at rest by default, they should be encrypted|
|[AWS060](/docs/aws/AWS060)|Athena workgroups should enforce configuration to prevent client disabling encryption|
|[AWS061](/docs/aws/AWS061)|API Gateway stages for V1 and V2 should have access logging enabled|
|[AWS062](/docs/aws/AWS062)|User data for EC2 instances must not contain sensitive AWS keys|
|[AWS063](/docs/aws/AWS063)|Cloudtrail should be enabled in all regions regardless of where your AWS resources are generally homed|
|[AWS064](/docs/aws/AWS064)|Cloudtrail log validation should be enabled to prevent tampering of log data|
|[AWS065](/docs/aws/AWS065)|Cloudtrail should be encrypted at rest to secure access to sensitive trail data|
|[AWS066](/docs/aws/AWS066)|EKS should have the encryption of secrets enabled|
|[AWS067](/docs/aws/AWS067)|EKS Clusters should have cluster control plane logging turned on|
|[AWS068](/docs/aws/AWS068)|EKS cluster should not have open CIDR range for public access|
|[AWS069](/docs/aws/AWS069)|EKS Clusters should have the public access disabled|
|[AWS070](/docs/aws/AWS070)|AWS ES Domain should have logging enabled|
|[AWS071](/docs/aws/AWS071)|Cloudfront distribution should have Access Logging configured|
|[AWS072](/docs/aws/AWS072)|Viewer Protocol Policy in Cloudfront Distribution Cache should always be set to HTTPS|
|[AWS073](/docs/aws/AWS073)|S3 Access Block should Ignore Public Acl|
|[AWS074](/docs/aws/AWS074)|S3 Access block should block public ACL|
|[AWS075](/docs/aws/AWS075)|S3 Access block should restrict public bucket to limit access|
|[AWS076](/docs/aws/AWS076)|S3 Access block should block public policy|
|[AWS077](/docs/aws/AWS077)|S3 Data should be versioned|
|[AWS078](/docs/aws/AWS078)|ECR images tags shouldn't be mutable.|
|[AWS079](/docs/aws/AWS079)|aws_instance should activate session tokens for Instance Metadata Service.|
|[AWS080](/docs/aws/AWS080)|CodeBuild Project artifacts encryption should not be disabled|
|[AWS081](/docs/aws/AWS081)|DAX Cluster should always encrypt data at rest|
|[AWS082](/docs/aws/AWS082)|It is AWS best practice to not use the default VPC for workflows|
|[AWS083](/docs/aws/AWS083)|Load balancers should drop invalid headers|
|[AWS084](/docs/aws/AWS084)|Root and user volumes on Workspaces should be encrypted|
|[AWS085](/docs/aws/AWS085)|Config configuration aggregator should be using all regions for source|
|[AWS086](/docs/aws/AWS086)|Point in time recovery should be enabled to protect DynamoDB table|
|[AWS087](/docs/aws/AWS087)|Redshift cluster should be deployed into a specific VPC|
|[AWS088](/docs/aws/AWS088)|Redis cluster should be backup retention turned on|
|[AWS089](/docs/aws/AWS089)|CloudWatch log groups should be encrypted using CMK|
|[AWS090](/docs/aws/AWS090)|ECS clusters should have container insights enabled|
|[AWS091](/docs/aws/AWS091)|RDS Cluster and RDS instance should have backup retention longer than default 1 day|
|[AWS092](/docs/aws/AWS092)|DynamoDB tables should use at rest encyption with a Customer Managed Key|
|[AWS093](/docs/aws/AWS093)|ECR Repository should use customer managed keys to allow more control|
|[AWS094](/docs/aws/AWS094)|Redshift clusters should use at rest encryption|
|[AWS095](/docs/aws/AWS095)|Secrets Manager should use customer managed keys|
|[AWS096](/docs/aws/AWS096)|ECS Task Definitions with EFS volumes should use in-transit encryption|
|[AWS097](/docs/aws/AWS097)|IAM customer managed policies should not allow decryption actions on all KMS keys|
|[AWS098](/docs/aws/AWS098)|S3 buckets should each define an aws_s3_bucket_public_access_block|

