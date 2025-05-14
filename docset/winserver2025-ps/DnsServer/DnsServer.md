---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
Download Help Link: https://aka.ms/winsvr-2025-pshelp
Help Version: 5.0.5.2
Locale: en-US
Module Guid: 46f598e5-9907-42b2-afbb-68e5f7e34604
Module Name: DnsServer
ms.date: 12/20/2016
title: DnsServer
---

# DnsServer Module
## Description
This reference provides cmdlet descriptions and syntax for all DNS Server cmdlets. It lists the cmdlets in alphabetical order based on the verb at the beginning of the cmdlet.
DnsServer Module can be obtained either by installing DNS Server role or adding the DNS Server Tools part of Remote Server Administration Tools (RSAT) feature.

## DnsServer Cmdlets
### [Add-DnsServerClientSubnet](./Add-DnsServerClientSubnet.md)
Adds a client subnet to a DNS server.

### [Add-DnsServerConditionalForwarderZone](./Add-DnsServerConditionalForwarderZone.md)
Adds a conditional forwarder to a DNS server.

### [Add-DnsServerDirectoryPartition](./Add-DnsServerDirectoryPartition.md)
Creates a DNS application directory partition.

### [Add-DnsServerForwarder](./Add-DnsServerForwarder.md)
Adds server level forwarders to a DNS server.

### [Add-DnsServerPrimaryZone](./Add-DnsServerPrimaryZone.md)
Adds a primary zone to a DNS server.

### [Add-DnsServerQueryResolutionPolicy](./Add-DnsServerQueryResolutionPolicy.md)
Adds a policy for query resolution to a DNS server.

### [Add-DnsServerRecursionScope](./Add-DnsServerRecursionScope.md)
Adds a recursion scope on a DNS server.

### [Add-DnsServerResourceRecord](./Add-DnsServerResourceRecord.md)
Adds a resource record of a specified type to a specified DNS zone.

### [Add-DnsServerResourceRecordA](./Add-DnsServerResourceRecordA.md)
Adds a type A resource record to a DNS zone.

### [Add-DnsServerResourceRecordAAAA](./Add-DnsServerResourceRecordAAAA.md)
Adds a type AAAA resource record to a DNS server.

### [Add-DnsServerResourceRecordCName](./Add-DnsServerResourceRecordCName.md)
Adds a type CNAME resource record to a DNS  zone.

### [Add-DnsServerResourceRecordDnsKey](./Add-DnsServerResourceRecordDnsKey.md)
Adds a type DNSKEY resource record to a DNS zone.

### [Add-DnsServerResourceRecordDS](./Add-DnsServerResourceRecordDS.md)
Adds a type DS resource record to a DNS zone.

### [Add-DnsServerResourceRecordMX](./Add-DnsServerResourceRecordMX.md)
Adds an MX resource record to a DNS server.

### [Add-DnsServerResourceRecordPtr](./Add-DnsServerResourceRecordPtr.md)
Adds a type PTR resource record to a DNS server.

### [Add-DnsServerResponseRateLimitingExceptionlist](./Add-DnsServerResponseRateLimitingExceptionlist.md)
Adds an RRL exception list on the DNS server.

### [Add-DnsServerRootHint](./Add-DnsServerRootHint.md)
Adds root hints on a DNS server.

### [Add-DnsServerSecondaryZone](./Add-DnsServerSecondaryZone.md)
Adds a DNS server secondary zone.

### [Add-DnsServerSigningKey](./Add-DnsServerSigningKey.md)
Adds a KSK or ZSK to a signed zone.

### [Add-DnsServerStubZone](./Add-DnsServerStubZone.md)
Adds a DNS stub zone.

### [Add-DnsServerTrustAnchor](./Add-DnsServerTrustAnchor.md)
Adds a trust anchor to a DNS server.

### [Add-DnsServerVirtualizationInstance](./Add-DnsServerVirtualizationInstance.md)
Adds a virtualization instance.

### [Add-DnsServerZoneDelegation](./Add-DnsServerZoneDelegation.md)
Adds a new delegated DNS zone to an existing zone.

### [Add-DnsServerZoneScope](./Add-DnsServerZoneScope.md)
Adds a zone scope to an existing zone.

### [Add-DnsServerZoneTransferPolicy](./Add-DnsServerZoneTransferPolicy.md)
Adds a zone transfer policy to a DNS server.

### [Clear-DnsServerCache](./Clear-DnsServerCache.md)
Clears resource records from a cache on the DNS server.

### [Clear-DnsServerStatistics](./Clear-DnsServerStatistics.md)
Clears all DNS server statistics or statistics for zones.

### [ConvertTo-DnsServerPrimaryZone](./ConvertTo-DnsServerPrimaryZone.md)
Converts a zone to a DNS primary zone.

### [ConvertTo-DnsServerSecondaryZone](./ConvertTo-DnsServerSecondaryZone.md)
Converts a primary zone or stub zone to a secondary zone.

### [Disable-DnsServerPolicy](./Disable-DnsServerPolicy.md)
Disables DNS server policies.

### [Disable-DnsServerSigningKeyRollover](./Disable-DnsServerSigningKeyRollover.md)
Disables key rollover on an input key.

### [Enable-DnsServerPolicy](./Enable-DnsServerPolicy.md)
Enables DNS server policies.

### [Enable-DnsServerSigningKeyRollover](./Enable-DnsServerSigningKeyRollover.md)
Enables rollover on the input key.

### [Export-DnsServerDnsSecPublicKey](./Export-DnsServerDnsSecPublicKey.md)
Exports DS and DNSKEY information for a DNSSEC-signed zone.

### [Export-DnsServerZone](./Export-DnsServerZone.md)
Exports contents of a zone to a file.

### [Get-DnsServer](./Get-DnsServer.md)
Retrieves a DNS server configuration.

### [Get-DnsServerCache](./Get-DnsServerCache.md)
Retrieves DNS server cache settings.

### [Get-DnsServerClientSubnet](./Get-DnsServerClientSubnet.md)
Gets client subnets for a DNS server.

### [Get-DnsServerDiagnostics](./Get-DnsServerDiagnostics.md)
Retrieves DNS event logging details.

### [Get-DnsServerDirectoryPartition](./Get-DnsServerDirectoryPartition.md)
Gets a DNS application directory partition.

### [Get-DnsServerDnsSecZoneSetting](./Get-DnsServerDnsSecZoneSetting.md)
Gets DNSSEC settings for a zone.

### [Get-DnsServerDsSetting](./Get-DnsServerDsSetting.md)
Retrieves DNS Server Active Directory settings

### [Get-DnsServerEDns](./Get-DnsServerEDns.md)
Gets EDNS configuration settings on a DNS server.

### [Get-DnsServerForwarder](./Get-DnsServerForwarder.md)
Gets forwarder configuration settings on a DNS server.

### [Get-DnsServerGlobalNameZone](./Get-DnsServerGlobalNameZone.md)
Retrieves DNS server GlobalName zone configuration details.

### [Get-DnsServerGlobalQueryBlockList](./Get-DnsServerGlobalQueryBlockList.md)
Gets a global query block list.

### [Get-DnsServerQueryResolutionPolicy](./Get-DnsServerQueryResolutionPolicy.md)
Gets policies for query resolution from a DNS server.

### [Get-DnsServerRecursion](./Get-DnsServerRecursion.md)
Retrieves DNS server recursion settings.

### [Get-DnsServerRecursionScope](./Get-DnsServerRecursionScope.md)
Gets the DNS server recursion scopes.

### [Get-DnsServerResourceRecord](./Get-DnsServerResourceRecord.md)
Gets resource records from a specified DNS zone.

### [Get-DnsServerResponseRateLimiting](./Get-DnsServerResponseRateLimiting.md)
Displays the RRL settings on a DNS server.

### [Get-DnsServerResponseRateLimitingExceptionlist](./Get-DnsServerResponseRateLimitingExceptionlist.md)
Enumerates the RRL exception lists on a DNS Server.

### [Get-DnsServerRootHint](./Get-DnsServerRootHint.md)
Gets root hints on a DNS server.

### [Get-DnsServerScavenging](./Get-DnsServerScavenging.md)
Gets DNS aging and scavenging settings.

### [Get-DnsServerSetting](./Get-DnsServerSetting.md)
Retrieves DNS server settings.

### [Get-DnsServerSigningKey](./Get-DnsServerSigningKey.md)
Gets zone signing keys.

### [Get-DnsServerStatistics](./Get-DnsServerStatistics.md)
Retrieves DNS server statistics or statistics for zones.

### [Get-DnsServerTrustAnchor](./Get-DnsServerTrustAnchor.md)
Gets trust anchors on a DNS server.

### [Get-DnsServerTrustPoint](./Get-DnsServerTrustPoint.md)
Gets trust points on a DNS server.

### [Get-DnsServerVirtualizationInstance](./Get-DnsServerVirtualizationInstance.md)
Gets the virtualization instances on the DNS server.

### [Get-DnsServerZone](./Get-DnsServerZone.md)
Gets details of DNS zones on a DNS server.

### [Get-DnsServerZoneAging](./Get-DnsServerZoneAging.md)
Gets DNS aging settings for a zone.

### [Get-DnsServerZoneDelegation](./Get-DnsServerZoneDelegation.md)
Gets the zone delegations of a DNS server zone.

### [Get-DnsServerZoneScope](./Get-DnsServerZoneScope.md)
Gets the scopes of a zone on a DNS server.

### [Get-DnsServerZoneTransferPolicy](./Get-DnsServerZoneTransferPolicy.md)
Gets the zone transfer policies on a DNS server.

### [Import-DnsServerResourceRecordDS](./Import-DnsServerResourceRecordDS.md)
Imports DS resource record information from a file.

### [Import-DnsServerRootHint](./Import-DnsServerRootHint.md)
Copies root hints from a DNS server.

### [Import-DnsServerTrustAnchor](./Import-DnsServerTrustAnchor.md)
Imports a trust anchor for a DNS server.

### [Invoke-DnsServerSigningKeyRollover](./Invoke-DnsServerSigningKeyRollover.md)
Initiates rollover of signing keys for the zone.

### [Invoke-DnsServerZoneSign](./Invoke-DnsServerZoneSign.md)
Signs a DNS server zone.

### [Invoke-DnsServerZoneUnsign](./Invoke-DnsServerZoneUnsign.md)
Unsigns a DNS server zone.

### [Register-DnsServerDirectoryPartition](./Register-DnsServerDirectoryPartition.md)
Registers a DNS server in a DNS application directory partition.

### [Remove-DnsServerClientSubnet](./Remove-DnsServerClientSubnet.md)
Removes a client subnet from a DNS server.

### [Remove-DnsServerDirectoryPartition](./Remove-DnsServerDirectoryPartition.md)
Removes a DNS application directory partition.

### [Remove-DnsServerForwarder](./Remove-DnsServerForwarder.md)
Removes server level forwarders from a DNS server.

### [Remove-DnsServerQueryResolutionPolicy](./Remove-DnsServerQueryResolutionPolicy.md)
Removes a policy for query resolution from a DNS server.

### [Remove-DnsServerRecursionScope](./Remove-DnsServerRecursionScope.md)
Removes a recursion scope from a DNS server.

### [Remove-DnsServerResourceRecord](./Remove-DnsServerResourceRecord.md)
Removes specified DNS server resource records from a zone.

### [Remove-DnsServerResponseRateLimitingExceptionlist](./Remove-DnsServerResponseRateLimitingExceptionlist.md)
Removes an RRL exception list from a DNS server.

### [Remove-DnsServerRootHint](./Remove-DnsServerRootHint.md)
Removes root hints from a DNS server.

### [Remove-DnsServerSigningKey](./Remove-DnsServerSigningKey.md)
Removes signing keys.

### [Remove-DnsServerTrustAnchor](./Remove-DnsServerTrustAnchor.md)
Removes a trust anchor from a DNS server.

### [Remove-DnsServerVirtualizationInstance](./Remove-DnsServerVirtualizationInstance.md)
Removes a virtualization instance.

### [Remove-DnsServerZone](./Remove-DnsServerZone.md)
Removes a zone from a DNS server.

### [Remove-DnsServerZoneDelegation](./Remove-DnsServerZoneDelegation.md)
Removes a name server or delegation from a DNS zone.

### [Remove-DnsServerZoneScope](./Remove-DnsServerZoneScope.md)
Removes a zone scope from an existing zone.

### [Remove-DnsServerZoneTransferPolicy](./Remove-DnsServerZoneTransferPolicy.md)
Removes a zone transfer policy from a DNS server.

### [Reset-DnsServerZoneKeyMasterRole](./Reset-DnsServerZoneKeyMasterRole.md)
Transfers the role of Key Master for a DNS zone.

### [Restore-DnsServerPrimaryZone](./Restore-DnsServerPrimaryZone.md)
Restores primary DNS zone contents from Active Directory or from a file.

### [Restore-DnsServerSecondaryZone](./Restore-DnsServerSecondaryZone.md)
Restores secondary zone information from its source.

### [Resume-DnsServerZone](./Resume-DnsServerZone.md)
Resumes name resolution on a suspended zone.

### [Set-DnsServer](./Set-DnsServer.md)
Overwrites a DNS server configuration.

### [Set-DnsServerCache](./Set-DnsServerCache.md)
Modifies cache settings for a DNS server.

### [Set-DnsServerClientSubnet](./Set-DnsServerClientSubnet.md)
Updates the IP addresses in a client subnet.

### [Set-DnsServerConditionalForwarderZone](./Set-DnsServerConditionalForwarderZone.md)
Changes settings for a DNS conditional forwarder.

### [Set-DnsServerDiagnostics](./Set-DnsServerDiagnostics.md)
Sets debugging and logging parameters.

### [Set-DnsServerDnsSecZoneSetting](./Set-DnsServerDnsSecZoneSetting.md)
Changes settings for DNSSEC for a zone.

### [Set-DnsServerDsSetting](./Set-DnsServerDsSetting.md)
Modifies DNS Active Directory settings.

### [Set-DnsServerEDns](./Set-DnsServerEDns.md)
Changes EDNS settings on a DNS server.

### [Set-DnsServerForwarder](./Set-DnsServerForwarder.md)
Changes forwarder settings on a DNS server.

### [Set-DnsServerGlobalNameZone](./Set-DnsServerGlobalNameZone.md)
Changes configuration settings for a GlobalNames zone.

### [Set-DnsServerGlobalQueryBlockList](./Set-DnsServerGlobalQueryBlockList.md)
Changes settings of a global query block list.

### [Set-DnsServerPrimaryZone](./Set-DnsServerPrimaryZone.md)
Changes settings for a DNS primary zone.

### [Set-DnsServerQueryResolutionPolicy](./Set-DnsServerQueryResolutionPolicy.md)
Updates settings of a query resolution policy on a DNS server.

### [Set-DnsServerRecursion](./Set-DnsServerRecursion.md)
Modifies recursion settings for a DNS server.

### [Set-DnsServerRecursionScope](./Set-DnsServerRecursionScope.md)
Modifies a recursion scope on a DNS server.

### [Set-DnsServerResourceRecord](./Set-DnsServerResourceRecord.md)
Changes a resource record in a DNS zone.

### [Set-DnsServerResourceRecordAging](./Set-DnsServerResourceRecordAging.md)
Begins aging of resource records in a specified DNS zone.

### [Set-DnsServerResponseRateLimiting](./Set-DnsServerResponseRateLimiting.md)
Enables RRL on a DNS server.

### [Set-DnsServerResponseRateLimitingExceptionlist](./Set-DnsServerResponseRateLimitingExceptionlist.md)
Updates the settings of an RRL exception list.

### [Set-DnsServerRootHint](./Set-DnsServerRootHint.md)
Replaces a list of root hints.

### [Set-DnsServerScavenging](./Set-DnsServerScavenging.md)
Changes DNS server scavenging settings.

### [Set-DnsServerSecondaryZone](./Set-DnsServerSecondaryZone.md)
Changes settings for a DNS secondary zone.

### [Set-DnsServerSetting](./Set-DnsServerSetting.md)
Modifies DNS server settings.

### [Set-DnsServerSigningKey](./Set-DnsServerSigningKey.md)
Changes settings of a signing key.

### [Set-DnsServerStubZone](./Set-DnsServerStubZone.md)
Changes settings for a DNS server stub zone.

### [Set-DnsServerVirtualizationInstance](./Set-DnsServerVirtualizationInstance.md)
Updates the virtualization instance on the DNS server.

### [Set-DnsServerZoneAging](./Set-DnsServerZoneAging.md)
Configures DNS aging settings for a zone.

### [Set-DnsServerZoneDelegation](./Set-DnsServerZoneDelegation.md)
Changes delegation settings for a child zone.

### [Set-DnsServerZoneTransferPolicy](./Set-DnsServerZoneTransferPolicy.md)
Updates a zone transfer policy on a DNS server.

### [Show-DnsServerCache](./Show-DnsServerCache.md)
Shows the records in a DNS Server Cache.

### [Show-DnsServerKeyStorageProvider](./Show-DnsServerKeyStorageProvider.md)
Returns a list of key storage providers.

### [Start-DnsServerScavenging](./Start-DnsServerScavenging.md)
Notifies a DNS server to attempt a search for stale resource records.

### [Start-DnsServerZoneTransfer](./Start-DnsServerZoneTransfer.md)
Starts a zone transfer for a secondary DNS zone from master servers.

### [Step-DnsServerSigningKeyRollover](./Step-DnsServerSigningKeyRollover.md)
Rolls over a KSK that is waiting for a parent DS update.

### [Suspend-DnsServerZone](./Suspend-DnsServerZone.md)
Suspends a zone on a DNS server.

### [Sync-DnsServerZone](./Sync-DnsServerZone.md)
Checks the DNS server memory for changes, and writes them to persistent storage.

### [Test-DnsServer](./Test-DnsServer.md)
Tests that a specified computer is a functioning DNS server.

### [Test-DnsServerDnsSecZoneSetting](./Test-DnsServerDnsSecZoneSetting.md)
Validates DNSSEC settings for a zone.

### [Unregister-DnsServerDirectoryPartition](./Unregister-DnsServerDirectoryPartition.md)
Deregisters a DNS server from a DNS application directory partition.

### [Update-DnsServerTrustPoint](./Update-DnsServerTrustPoint.md)
Updates all trust points in a DNS trust anchor zone.



