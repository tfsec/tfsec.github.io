---
title: Azure Checks
permalink: /docs/azure/home/
has_children: true
has_toc: false
---

The included Azure checks are listed below. For more information about each check, see the link provided.

| ID  | Summary |
|:-------|:-------------|
|[azure-appservice-enforce-https](/docs/azure/azure-appservice-enforce-https)|Ensure the Function App can only be accessed via HTTPS. The default is false.|
|[azure-compute-enable-disk-encryption](/docs/azure/azure-compute-enable-disk-encryption)|Unencrypted managed disk.|
|[azure-compute-ssh-authentication](/docs/azure/azure-compute-ssh-authentication)|Password authentication in use instead of SSH keys.|
|[azure-container-configured-network-policy](/docs/azure/azure-container-configured-network-policy)|Ensure AKS cluster has Network Policy configured|
|[azure-container-limit-authorized-ips](/docs/azure/azure-container-limit-authorized-ips)|Ensure AKS has an API Server Authorized IP Ranges enabled|
|[azure-container-logging](/docs/azure/azure-container-logging)|Ensure AKS logging to Azure Monitoring is Configured|
|[azure-container-use-rbac-permissions](/docs/azure/azure-container-use-rbac-permissions)|Ensure RBAC is enabled on AKS clusters|
|[azure-database-enable-audit](/docs/azure/azure-database-enable-audit)|Auditing should be enabled on Azure SQL Databases|
|[azure-database-retention-period-set](/docs/azure/azure-database-retention-period-set)|Database auditing rentention period should be longer than 90 days|
|[azure-datafactory-no-public-access](/docs/azure/azure-datafactory-no-public-access)|Data Factory should have public access disabled, the default is enabled.|
|[azure-datalake-enable-at-rest-encryption](/docs/azure/azure-datalake-enable-at-rest-encryption)|Unencrypted data lake storage.|
|[azure-keyvault-content-type-for-secret](/docs/azure/azure-keyvault-content-type-for-secret)|Key vault Secret should have a content type set|
|[azure-keyvault-ensure-key-expiry](/docs/azure/azure-keyvault-ensure-key-expiry)|Ensure that the expiration date is set on all keys|
|[azure-keyvault-ensure-secret-expiry](/docs/azure/azure-keyvault-ensure-secret-expiry)|Key Vault Secret should have an expiration date set|
|[azure-keyvault-no-purge](/docs/azure/azure-keyvault-no-purge)|Key vault should have purge protection enabled|
|[azure-keyvault-specify-network-acl](/docs/azure/azure-keyvault-specify-network-acl)|Key vault should have the network acl block specified|
|[azure-network-disable-rdp-from-internet](/docs/azure/azure-network-disable-rdp-from-internet)|RDP access should not be accessible from the Internet, should be blocked on port 3389|
|[azure-network-no-public-egress](/docs/azure/azure-network-no-public-egress)|An outbound network security rule allows traffic to /0.|
|[azure-network-no-public-ingress](/docs/azure/azure-network-no-public-ingress)|An inbound network security rule allows traffic from /0.|
|[azure-network-ssh-blocked-from-internet](/docs/azure/azure-network-ssh-blocked-from-internet)|SSH access should not be accessible from the Internet, should be blocked on port 22|
|[azure-storage-allow-microsoft-service-bypass](/docs/azure/azure-storage-allow-microsoft-service-bypass)|Trusted Microsoft Services should have bypass access to Storage accounts|
|[azure-storage-default-action-deny](/docs/azure/azure-storage-default-action-deny)|The default action on Storage account network rules should be set to deny|
|[azure-storage-enforce-https](/docs/azure/azure-storage-enforce-https)|Storage accounts should be configured to only accept transfers that are over secure connections|
|[azure-storage-ensure-https](/docs/azure/azure-storage-ensure-https)|Ensure HTTPS is enabled on Azure Storage Account|
|[azure-storage-no-public-access](/docs/azure/azure-storage-no-public-access)|Storage containers in blob storage mode should not have public access|
|[azure-storage-queue-services-logging-enabled](/docs/azure/azure-storage-queue-services-logging-enabled)|When using Queue Services for a storage account, logging should be enabled.|
|[azure-storage-use-secure-tls-policy](/docs/azure/azure-storage-use-secure-tls-policy)|The minimum TLS version for Storage Accounts should be TLS1_2|
|[azure-synapse-virtual-network-enabled](/docs/azure/azure-synapse-virtual-network-enabled)|Synapse Workspace should have managed virtual network enabled, the default is disabled.|

