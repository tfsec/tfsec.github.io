---
title: AWS Checks
permalink: /docs/aws/home/
has_children: true
has_toc: false
---

The included AWS checks are listed below. For more information about each check, see the link provided.

| ID  | Summary |
|:-------|:-------------|
|[aws-api-gateway-enable-access-logging](/docs/aws/aws-api-gateway-enable-access-logging)|API Gateway stages for V1 and V2 should have access logging enabled|
|[aws-api-gateway-use-secure-tls-policy](/docs/aws/aws-api-gateway-use-secure-tls-policy)|API Gateway domain name uses outdated SSL/TLS protocols.|
|[aws-athena-enable-at-rest-encryption](/docs/aws/aws-athena-enable-at-rest-encryption)|Athena databases and workgroup configurations are created unencrypted at rest by default, they should be encrypted|
|[aws-athena-no-encryption-override](/docs/aws/aws-athena-no-encryption-override)|Athena workgroups should enforce configuration to prevent client disabling encryption|
|[aws-autoscaling-enable-at-rest-encryption](/docs/aws/aws-autoscaling-enable-at-rest-encryption)|Launch configuration with unencrypted block device.|
|[aws-autoscaling-no-public-ip](/docs/aws/aws-autoscaling-no-public-ip)|A resource has a public IP address.|
|[aws-cloudfront-enable-logging](/docs/aws/aws-cloudfront-enable-logging)|Cloudfront distribution should have Access Logging configured|
|[aws-cloudfront-enable-waf](/docs/aws/aws-cloudfront-enable-waf)|CloudFront distribution does not have a WAF in front.|
|[aws-cloudfront-enforce-https](/docs/aws/aws-cloudfront-enforce-https)|CloudFront distribution allows unencrypted (HTTP) communications.|
|[aws-cloudfront-use-secure-tls-policy](/docs/aws/aws-cloudfront-use-secure-tls-policy)|CloudFront distribution uses outdated SSL/TLS protocols.|
|[aws-cloudtrail-enable-all-regions](/docs/aws/aws-cloudtrail-enable-all-regions)|Cloudtrail should be enabled in all regions regardless of where your AWS resources are generally homed|
|[aws-cloudtrail-enable-at-rest-encryption](/docs/aws/aws-cloudtrail-enable-at-rest-encryption)|Cloudtrail should be encrypted at rest to secure access to sensitive trail data|
|[aws-cloudtrail-enable-log-validation](/docs/aws/aws-cloudtrail-enable-log-validation)|Cloudtrail log validation should be enabled to prevent tampering of log data|
|[aws-cloudwatch-log-group-customer-key](/docs/aws/aws-cloudwatch-log-group-customer-key)|CloudWatch log groups should be encrypted using CMK|
|[aws-codebuild-enable-encryption](/docs/aws/aws-codebuild-enable-encryption)|CodeBuild Project artifacts encryption should not be disabled|
|[aws-config-aggregate-all-regions](/docs/aws/aws-config-aggregate-all-regions)|Config configuration aggregator should be using all regions for source|
|[aws-dynamodb-enable-at-rest-encryption](/docs/aws/aws-dynamodb-enable-at-rest-encryption)|DAX Cluster should always encrypt data at rest|
|[aws-dynamodb-enable-recovery](/docs/aws/aws-dynamodb-enable-recovery)|Point in time recovery should be enabled to protect DynamoDB table|
|[aws-dynamodb-table-customer-key](/docs/aws/aws-dynamodb-table-customer-key)|DynamoDB tables should use at rest encryption with a Customer Managed Key|
|[aws-ec2-enforce-http-token-imds](/docs/aws/aws-ec2-enforce-http-token-imds)|aws_instance should activate session tokens for Instance Metadata Service.|
|[aws-ec2-no-secrets-in-user-data](/docs/aws/aws-ec2-no-secrets-in-user-data)|User data for EC2 instances must not contain sensitive AWS keys|
|[aws-ecr-enable-image-scans](/docs/aws/aws-ecr-enable-image-scans)|ECR repository has image scans disabled.|
|[aws-ecr-enforce-immutable-repository](/docs/aws/aws-ecr-enforce-immutable-repository)|ECR images tags shouldn't be mutable.|
|[aws-ecr-repository-customer-key](/docs/aws/aws-ecr-repository-customer-key)|ECR Repository should use customer managed keys to allow more control|
|[aws-ecs-enable-container-insight](/docs/aws/aws-ecs-enable-container-insight)|ECS clusters should have container insights enabled|
|[aws-ecs-enable-in-transit-encryption](/docs/aws/aws-ecs-enable-in-transit-encryption)|ECS Task Definitions with EFS volumes should use in-transit encryption|
|[aws-ecs-no-plaintext-secrets](/docs/aws/aws-ecs-no-plaintext-secrets)|Task definition defines sensitive environment variable(s).|
|[aws-efs-enable-at-rest-encryption](/docs/aws/aws-efs-enable-at-rest-encryption)|EFS Encryption has not been enabled|
|[aws-eks-enable-control-plane-logging](/docs/aws/aws-eks-enable-control-plane-logging)|EKS Clusters should have cluster control plane logging turned on|
|[aws-eks-encrypt-secrets](/docs/aws/aws-eks-encrypt-secrets)|EKS should have the encryption of secrets enabled|
|[aws-eks-no-public-cluster-access](/docs/aws/aws-eks-no-public-cluster-access)|EKS Clusters should have the public access disabled|
|[aws-eks-no-public-cluster-access-to-cidr](/docs/aws/aws-eks-no-public-cluster-access-to-cidr)|EKS cluster should not have open CIDR range for public access|
|[aws-elastic-search-enable-domain-logging](/docs/aws/aws-elastic-search-enable-domain-logging)|Domain logging should be enabled for Elastic Search domains|
|[aws-elastic-search-enable-in-transit-encryption](/docs/aws/aws-elastic-search-enable-in-transit-encryption)|Elasticsearch domain uses plaintext traffic for node to node communication.|
|[aws-elastic-search-enable-logging](/docs/aws/aws-elastic-search-enable-logging)|AWS ES Domain should have logging enabled|
|[aws-elastic-search-encrypt-replication-group](/docs/aws/aws-elastic-search-encrypt-replication-group)|Unencrypted Elasticache Replication Group.|
|[aws-elastic-search-enforce-https](/docs/aws/aws-elastic-search-enforce-https)|Elasticsearch doesn't enforce HTTPS traffic.|
|[aws-elastic-search-use-secure-tls-policy](/docs/aws/aws-elastic-search-use-secure-tls-policy)|Elasticsearch domain endpoint is using outdated TLS policy.|
|[aws-elastic-service-enable-domain-encryption](/docs/aws/aws-elastic-service-enable-domain-encryption)|Elasticsearch domain isn't encrypted at rest.|
|[aws-elasticache-enable-backup-retention](/docs/aws/aws-elasticache-enable-backup-retention)|Redis cluster should have backup retention turned on|
|[aws-elasticache-enable-in-transit-encryption](/docs/aws/aws-elasticache-enable-in-transit-encryption)|Elasticache Replication Group uses unencrypted traffic.|
|[aws-elb-drop-invalid-headers](/docs/aws/aws-elb-drop-invalid-headers)|Load balancers should drop invalid headers|
|[aws-elbv2-alb-not-public](/docs/aws/aws-elbv2-alb-not-public)|Load balancer is exposed to the internet.|
|[aws-elbv2-http-not-used](/docs/aws/aws-elbv2-http-not-used)|Use of plain HTTP.|
|[aws-iam-block-kms-policy-wildcard](/docs/aws/aws-iam-block-kms-policy-wildcard)|IAM customer managed policies should not allow decryption actions on all KMS keys|
|[aws-iam-no-password-reuse](/docs/aws/aws-iam-no-password-reuse)|IAM Password policy should prevent password reuse.|
|[aws-iam-no-policy-wildcards](/docs/aws/aws-iam-no-policy-wildcards)|IAM policy should avoid use of wildcards and instead apply the principle of least privilege|
|[aws-iam-require-lowercase-in-passwords](/docs/aws/aws-iam-require-lowercase-in-passwords)|IAM Password policy should have requirement for at least one lowercase character.|
|[aws-iam-require-numbers-in-passwords](/docs/aws/aws-iam-require-numbers-in-passwords)|IAM Password policy should have requirement for at least one number in the password.|
|[aws-iam-require-symbols-in-passwords](/docs/aws/aws-iam-require-symbols-in-passwords)|IAM Password policy should have requirement for at least one symbol in the password.|
|[aws-iam-require-uppercase-in-passwords](/docs/aws/aws-iam-require-uppercase-in-passwords)|IAM Password policy should have requirement for at least one uppercase character.|
|[aws-iam-set-max-password-age](/docs/aws/aws-iam-set-max-password-age)|IAM Password policy should have expiry less than or equal to 90 days.|
|[aws-iam-set-minimum-password-length](/docs/aws/aws-iam-set-minimum-password-length)|IAM Password policy should have minimum password length of 14 or more characters.|
|[aws-kinesis-enable-in-transit-encryption](/docs/aws/aws-kinesis-enable-in-transit-encryption)|Kinesis stream is unencrypted.|
|[aws-kms-auto-rotate-keys](/docs/aws/aws-kms-auto-rotate-keys)|A KMS key is not configured to auto-rotate.|
|[aws-lambda-restrict-source-arn](/docs/aws/aws-lambda-restrict-source-arn)|Ensure that lambda function permission has a source arn specified|
|[aws-misc-no-exposing-plaintext-credentials](/docs/aws/aws-misc-no-exposing-plaintext-credentials)|AWS provider has access credentials specified.|
|[aws-msk-enable-in-transit-encryption](/docs/aws/aws-msk-enable-in-transit-encryption)|A MSK cluster allows unencrypted data in transit.|
|[aws-rds-backup-retention-specified](/docs/aws/aws-rds-backup-retention-specified)|RDS Cluster and RDS instance should have backup retention longer than default 1 day|
|[aws-rds-enable-performance-insights](/docs/aws/aws-rds-enable-performance-insights)|Encryption for RDS Performance Insights should be enabled.|
|[aws-rds-encrypt-cluster-storage-data](/docs/aws/aws-rds-encrypt-cluster-storage-data)|There is no encryption specified or encryption is disabled on the RDS Cluster.|
|[aws-rds-encrypt-instance-storage-data](/docs/aws/aws-rds-encrypt-instance-storage-data)|RDS encryption has not been enabled at a DB Instance level.|
|[aws-rds-no-classic-resources](/docs/aws/aws-rds-no-classic-resources)|AWS Classic resource usage.|
|[aws-rds-no-public-db-access](/docs/aws/aws-rds-no-public-db-access)|A database resource is marked as publicly accessible.|
|[aws-redshift-encryption-customer-key](/docs/aws/aws-redshift-encryption-customer-key)|Redshift clusters should use at rest encryption|
|[aws-redshift-non-default-vpc-deployment](/docs/aws/aws-redshift-non-default-vpc-deployment)|Redshift cluster should be deployed into a specific VPC|
|[aws-s3-block-public-acls](/docs/aws/aws-s3-block-public-acls)|S3 Access block should block public ACL|
|[aws-s3-block-public-policy](/docs/aws/aws-s3-block-public-policy)|S3 Access block should block public policy|
|[aws-s3-enable-bucket-encryption](/docs/aws/aws-s3-enable-bucket-encryption)|Unencrypted S3 bucket.|
|[aws-s3-enable-bucket-logging](/docs/aws/aws-s3-enable-bucket-logging)|S3 Bucket does not have logging enabled.|
|[aws-s3-enable-versioning](/docs/aws/aws-s3-enable-versioning)|S3 Data should be versioned|
|[aws-s3-ignore-public-acls](/docs/aws/aws-s3-ignore-public-acls)|S3 Access Block should Ignore Public Acl|
|[aws-s3-no-public-access-with-acl](/docs/aws/aws-s3-no-public-access-with-acl)|S3 Bucket has an ACL defined which allows public access.|
|[aws-s3-no-public-buckets](/docs/aws/aws-s3-no-public-buckets)|S3 Access block should restrict public bucket to limit access|
|[aws-s3-specify-public-access-block](/docs/aws/aws-s3-specify-public-access-block)|S3 buckets should each define an aws_s3_bucket_public_access_block|
|[aws-sns-enable-topic-encryption](/docs/aws/aws-sns-enable-topic-encryption)|Unencrypted SNS topic.|
|[aws-sqs-enable-queue-encryption](/docs/aws/aws-sqs-enable-queue-encryption)|Unencrypted SQS queue.|
|[aws-sqs-no-wildcards-in-policy-documents](/docs/aws/aws-sqs-no-wildcards-in-policy-documents)|AWS SQS policy document has wildcard action statement.|
|[aws-ssm-secret-use-customer-key](/docs/aws/aws-ssm-secret-use-customer-key)|Secrets Manager should use customer managed keys|
|[aws-vpc-add-decription-to-security-group](/docs/aws/aws-vpc-add-decription-to-security-group)|Missing description for security group/security group rule.|
|[aws-vpc-no-default-vpc](/docs/aws/aws-vpc-no-default-vpc)|AWS best practice to not use the default VPC for workflows|
|[aws-vpc-no-excessive-port-access](/docs/aws/aws-vpc-no-excessive-port-access)|An ingress Network ACL rule allows ALL ports.|
|[aws-vpc-no-public-egress-sg](/docs/aws/aws-vpc-no-public-egress-sg)|An inline egress security group rule allows traffic to /0.|
|[aws-vpc-no-public-egress-sgr](/docs/aws/aws-vpc-no-public-egress-sgr)|An egress security group rule allows traffic to /0.|
|[aws-vpc-no-public-ingress](/docs/aws/aws-vpc-no-public-ingress)|An ingress Network ACL rule allows specific ports from /0.|
|[aws-vpc-no-public-ingress-sg](/docs/aws/aws-vpc-no-public-ingress-sg)|An inline ingress security group rule allows traffic from /0.|
|[aws-vpc-no-public-ingress-sgr](/docs/aws/aws-vpc-no-public-ingress-sgr)|An ingress security group rule allows traffic from /0.|
|[aws-vpc-use-secure-tls-policy](/docs/aws/aws-vpc-use-secure-tls-policy)|An outdated SSL policy is in use by a load balancer.|
|[aws-workspace-enable-disk-encryption](/docs/aws/aws-workspace-enable-disk-encryption)|Root and user volumes on Workspaces should be encrypted|

