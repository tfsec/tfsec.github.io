---
title: Azure Checks
permalink: /docs/azure/home/
has_children: true
has_toc: false
---

The included Azure checks are listed below. For more information about each check, see the link provided.

|  Azure Checks |
|:------------|
|[azure-appservice-enforce-https](/docs/azure/appservice/enforce-https)<br>Ensure the Function App can only be accessed via HTTPS. The default is false.|
|[azure-compute-enable-disk-encryption](/docs/azure/compute/enable-disk-encryption)<br>Unencrypted managed disk.|
|[azure-compute-ssh-authentication](/docs/azure/compute/ssh-authentication)<br>Password authentication in use instead of SSH keys.|
|[azure-container-configured-network-policy](/docs/azure/container/configured-network-policy)<br>Ensure AKS cluster has Network Policy configured|
|[azure-container-limit-authorized-ips](/docs/azure/container/limit-authorized-ips)<br>Ensure AKS has an API Server Authorized IP Ranges enabled|
|[azure-container-logging](/docs/azure/container/logging)<br>Ensure AKS logging to Azure Monitoring is Configured|
|[azure-container-use-rbac-permissions](/docs/azure/container/use-rbac-permissions)<br>Ensure RBAC is enabled on AKS clusters|
|[azure-database-enable-audit](/docs/azure/database/enable-audit)<br>Auditing should be enabled on Azure SQL Databases|
|[azure-database-retention-period-set](/docs/azure/database/retention-period-set)<br>Database auditing rentention period should be longer than 90 days|
|[azure-datafactory-no-public-access](/docs/azure/datafactory/no-public-access)<br>Data Factory should have public access disabled, the default is enabled.|
|[azure-datalake-enable-at-rest-encryption](/docs/azure/datalake/enable-at-rest-encryption)<br>Unencrypted data lake storage.|
|[azure-keyvault-content-type-for-secret](/docs/azure/keyvault/content-type-for-secret)<br>Key vault Secret should have a content type set|
|[azure-keyvault-ensure-key-expiry](/docs/azure/keyvault/ensure-key-expiry)<br>Ensure that the expiration date is set on all keys|
|[azure-keyvault-ensure-secret-expiry](/docs/azure/keyvault/ensure-secret-expiry)<br>Key Vault Secret should have an expiration date set|
|[azure-keyvault-no-purge](/docs/azure/keyvault/no-purge)<br>Key vault should have purge protection enabled|
|[azure-keyvault-specify-network-acl](/docs/azure/keyvault/specify-network-acl)<br>Key vault should have the network acl block specified|
|[azure-network-disable-rdp-from-internet](/docs/azure/network/disable-rdp-from-internet)<br>RDP access should not be accessible from the Internet, should be blocked on port 3389|
|[azure-network-no-public-egress](/docs/azure/network/no-public-egress)<br>An outbound network security rule allows traffic to /0.|
|[azure-network-no-public-ingress](/docs/azure/network/no-public-ingress)<br>An inbound network security rule allows traffic from /0.|
|[azure-network-ssh-blocked-from-internet](/docs/azure/network/ssh-blocked-from-internet)<br>SSH access should not be accessible from the Internet, should be blocked on port 22|
|[azure-storage-allow-microsoft-service-bypass](/docs/azure/storage/allow-microsoft-service-bypass)<br>Trusted Microsoft Services should have bypass access to Storage accounts|
|[azure-storage-default-action-deny](/docs/azure/storage/default-action-deny)<br>The default action on Storage account network rules should be set to deny|
|[azure-storage-enforce-https](/docs/azure/storage/enforce-https)<br>Storage accounts should be configured to only accept transfers that are over secure connections|
|[azure-storage-ensure-https](/docs/azure/storage/ensure-https)<br>Ensure HTTPS is enabled on Azure Storage Account|
|[azure-storage-no-public-access](/docs/azure/storage/no-public-access)<br>Storage containers in blob storage mode should not have public access|
|[azure-storage-queue-services-logging-enabled](/docs/azure/storage/queue-services-logging-enabled)<br>When using Queue Services for a storage account, logging should be enabled.|
|[azure-storage-use-secure-tls-policy](/docs/azure/storage/use-secure-tls-policy)<br>The minimum TLS version for Storage Accounts should be TLS1_2|
|[azure-synapse-virtual-network-enabled](/docs/azure/synapse/virtual-network-enabled)<br>Synapse Workspace should have managed virtual network enabled, the default is disabled.|
