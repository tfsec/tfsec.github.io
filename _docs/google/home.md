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
|[google-iam-no-user-granted-permissions](/docs/google/iam/no-user-granted-permissions)<br>IAM granted directly to user.|
|[google-storage-enable-ubla](/docs/google/storage/enable-ubla)<br>Ensure that Cloud Storage buckets have uniform bucket-level access enabled|
|[google-storage-no-public-access](/docs/google/storage/no-public-access)<br>Ensure that Cloud Storage bucket is not anonymously or publicly accessible.|
