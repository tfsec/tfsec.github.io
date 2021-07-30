---
title: Google Checks
permalink: /docs/google/home/
has_children: true
has_toc: false
---

The included Google checks are listed below. For more information about each check, see the link provided.

| Checks |
|:------------|
|[google-compute-disk-encryption-customer-keys](/docs/google/compute/disk-encryption-customer-keys)<br>Encrypted compute disk with unmanaged keys.|
|[google-compute-disk-encryption-required](/docs/google/compute/disk-encryption-required)<br>The encryption key used to encrypt a compute disk has been specified in plaintext.|
|[google-compute-no-public-egress](/docs/google/compute/no-public-egress)<br>An outbound firewall rule allows traffic to /0.|
|[google-compute-no-public-ingress](/docs/google/compute/no-public-ingress)<br>An inbound firewall rule allows traffic from /0.|
|[google-gke-enforce-pod-security-policy](/docs/google/gke/enforce-pod-security-policy)<br>Pod security policy enforcement not defined.|
|[google-gke-metadata-endpoints-disabled](/docs/google/gke/metadata-endpoints-disabled)<br>Legacy metadata endpoints enabled.|
|[google-gke-no-legacy-authentication](/docs/google/gke/no-legacy-authentication)<br>Legacy client authentication methods utilized.|
|[google-gke-node-metadata-security](/docs/google/gke/node-metadata-security)<br>Node metadata value disables metadata concealment.|
|[google-gke-node-shielding-enabled](/docs/google/gke/node-shielding-enabled)<br>Shielded GKE nodes not enabled.|
|[google-gke-use-rbac-permissions](/docs/google/gke/use-rbac-permissions)<br>Legacy ABAC permissions are enabled.|
|[google-gke-use-service-account](/docs/google/gke/use-service-account)<br>Checks for service account defined for GKE nodes|
|[google-iam-no-folder-level-default-service-account-assignment](/docs/google/iam/no-folder-level-default-service-account-assignment)<br>Roles should not be assigned to default service accounts|
|[google-iam-no-folder-level-service-account-impersonation](/docs/google/iam/no-folder-level-service-account-impersonation)<br>Users should not be granted service account access at the folder level|
|[google-iam-no-org-level-default-service-account-assignment](/docs/google/iam/no-org-level-default-service-account-assignment)<br>Roles should not be assigned to default service accounts|
|[google-iam-no-org-level-service-account-impersonation](/docs/google/iam/no-org-level-service-account-impersonation)<br>Users should not be granted service account access at the organization level|
|[google-iam-no-privileged-service-accounts](/docs/google/iam/no-privileged-service-accounts)<br>Service accounts should not have roles assigned with excessive privileges|
|[google-iam-no-project-level-default-service-account-assignment](/docs/google/iam/no-project-level-default-service-account-assignment)<br>Roles should not be assigned to default service accounts|
|[google-iam-no-project-level-service-account-impersonation](/docs/google/iam/no-project-level-service-account-impersonation)<br>Users should not be granted service account access at the project level|
|[google-iam-no-user-granted-permissions](/docs/google/iam/no-user-granted-permissions)<br>IAM granted directly to user.|
|[google-sql-enable-backup](/docs/google/sql/enable-backup)<br>Enable automated backups to recover from data-loss|
|[google-sql-enable-pg-temp-file-logging](/docs/google/sql/enable-pg-temp-file-logging)<br>Temporary file logging should be enabled for all temporary files.|
|[google-sql-encrypt-in-transit-data](/docs/google/sql/encrypt-in-transit-data)<br>SSL connections to a SQL database instance should be enforced.|
|[google-sql-mysql-no-local-infile](/docs/google/sql/mysql-no-local-infile)<br>Disable local_infile setting in MySQL|
|[google-sql-no-contained-db-auth](/docs/google/sql/no-contained-db-auth)<br>Contained database authentication should be disabled|
|[google-sql-no-cross-db-ownership-chaining](/docs/google/sql/no-cross-db-ownership-chaining)<br>Cross-database ownership chaining should be disabled|
|[google-sql-no-public-access](/docs/google/sql/no-public-access)<br>Ensure that Cloud SQL Database Instances are not publicly exposed|
|[google-sql-pg-log-checkpoints](/docs/google/sql/pg-log-checkpoints)<br>Ensure that logging of checkpoints is enabled.|
|[google-sql-pg-log-connections](/docs/google/sql/pg-log-connections)<br>Ensure that logging of connections is enabled.|
|[google-sql-pg-log-disconnections](/docs/google/sql/pg-log-disconnections)<br>Ensure that logging of disconnections is enabled.|
|[google-sql-pg-log-errors](/docs/google/sql/pg-log-errors)<br>Ensure that Postgres errors are logged|
|[google-sql-pg-log-lock-waits](/docs/google/sql/pg-log-lock-waits)<br>Ensure that logging of lock waits is enabled.|
|[google-sql-pg-no-min-statement-logging](/docs/google/sql/pg-no-min-statement-logging)<br>Ensure that logging of long statements is disabled.|
|[google-storage-enable-ubla](/docs/google/storage/enable-ubla)<br>Ensure that Cloud Storage buckets have uniform bucket-level access enabled|
|[google-storage-no-public-access](/docs/google/storage/no-public-access)<br>Ensure that Cloud Storage bucket is not anonymously or publicly accessible.|
