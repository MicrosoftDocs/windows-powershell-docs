---
Download Help Link: https://aka.ms/winsvr-2012r2-pshelp
Help Version: 4.0.3.0
Locale: en-US
Module Guid: 90eaa9df-133a-450c-8728-91055cd946a1
Module Name: DhcpServer
ms.date: 10/30/2017
title: DhcpServer
---

# DhcpServer Module
## Description
This reference provides cmdlet descriptions and syntax for all Dynamic Host Configuration Protocol (DHCP) server service-specific cmdlets. It lists the cmdlets in alphabetical order based on the verb at the beginning of the cmdlet. 

Also see [DHCP Classes](https://go.microsoft.com/FWLink/p/?LinkId=260590).

## DhcpServer Cmdlets
### [Add-DhcpServerInDC](./Add-DhcpServerInDC.md)
Adds the computer running the DHCP server service to the list of authorized Dynamic Host Configuration Protocol (DHCP) server services in Active Directory (AD).

### [Add-DhcpServerSecurityGroup](./Add-DhcpServerSecurityGroup.md)
Adds security groups to a DHCP server.

### [Add-DhcpServerv4Class](./Add-DhcpServerv4Class.md)
Adds an IPv4 vendor or user class to the Dynamic Host Configuration Protocol (DHCP) server service.

### [Add-DhcpServerv4ExclusionRange](./Add-DhcpServerv4ExclusionRange.md)
Adds a range of excluded IP addresses for an IPv4 scope.

### [Add-DhcpServerv4Failover](./Add-DhcpServerv4Failover.md)
Adds a new IPv4 failover relationship on the Dynamic Host Configuration Protocol (DHCP) server service.

### [Add-DhcpServerv4FailoverScope](./Add-DhcpServerv4FailoverScope.md)
Adds one or more specified scopes to the failover relationship.

### [Add-DhcpServerv4Filter](./Add-DhcpServerv4Filter.md)
Adds a MAC address filter to the Dynamic Host Configuration Protocol (DHCP) server service.

### [Add-DhcpServerv4Lease](./Add-DhcpServerv4Lease.md)
Adds a new IPv4 address lease in the Dynamic Host Configuration Protocol (DHCP) server service.

### [Add-DhcpServerv4MulticastExclusionRange](./Add-DhcpServerv4MulticastExclusionRange.md)
Adds a range of addresses to exclude from a multicast scope.

### [Add-DhcpServerv4MulticastScope](./Add-DhcpServerv4MulticastScope.md)
Adds a multicast scope on the DHCP server.

### [Add-DhcpServerv4OptionDefinition](./Add-DhcpServerv4OptionDefinition.md)
Adds a new DHCPv4 option definition on the Dynamic Host Configuration Protocol (DHCP) server service.

### [Add-DhcpServerv4Policy](./Add-DhcpServerv4Policy.md)
Adds a new policy either at the server level or at the scope level.

### [Add-DhcpServerv4PolicyIPRange](./Add-DhcpServerv4PolicyIPRange.md)
Adds an IP range to an existing policy at the scope level.

### [Add-DhcpServerv4Reservation](./Add-DhcpServerv4Reservation.md)
Reserves the specified IPv4 address in the scope for a client.

### [Add-DhcpServerv4Scope](./Add-DhcpServerv4Scope.md)
Adds an IPv4 scope on the Dynamic Host Configuration Protocol (DHCP) server service.

### [Add-DhcpServerv4Superscope](./Add-DhcpServerv4Superscope.md)
Adds one or more specified scopes to a superscope.

### [Add-DhcpServerv6Class](./Add-DhcpServerv6Class.md)
Adds an IPv6 vendor or user class to the Dynamic Host Configuration Protocol (DHCP) server service.

### [Add-DhcpServerv6ExclusionRange](./Add-DhcpServerv6ExclusionRange.md)
Sets the range of IPv6 addresses to exclude from an IPv6 scope.

### [Add-DhcpServerv6Lease](./Add-DhcpServerv6Lease.md)
Adds a new IPv6 address lease to the Dynamic Host Configuration Protocol (DHCP) server service.

### [Add-DhcpServerv6OptionDefinition](./Add-DhcpServerv6OptionDefinition.md)
Adds a DHCPv6 option definition to a Dynamic Host Configuration Protocol (DHCP) server service running on the local or a remote computer.

### [Add-DhcpServerv6Reservation](./Add-DhcpServerv6Reservation.md)
Adds an IPv6 Reservation to an IPv6 prefix or scope.

### [Add-DhcpServerv6Scope](./Add-DhcpServerv6Scope.md)
Adds an IPv6 scope to the Dynamic Host Configuration Protocol (DHCP) server service with the specified parameters.

### [Backup-DhcpServer](./Backup-DhcpServer.md)
Backs up the Dynamic Host Configuration Protocol (DHCP) database of DHCP server service to the specified location.

### [Export-DhcpServer](./Export-DhcpServer.md)
Exports the Dynamic Host Configuration Protocol (DHCP) server service configuration, and optionally lease data, to the specified file.

### [Get-DhcpServerAuditLog](./Get-DhcpServerAuditLog.md)
Gets the configuration parameters related to the audit log of the Dynamic Host Configuration Protocol (DHCP) server service.

### [Get-DhcpServerDatabase](./Get-DhcpServerDatabase.md)
Gets the configuration parameters related to the database of the Dynamic Host Configuration Protocol (DHCP) server service.

### [Get-DhcpServerDnsCredential](./Get-DhcpServerDnsCredential.md)
Gets an account that the DHCP Server service uses to register or deregister client records on a DNS server.

### [Get-DhcpServerInDC](./Get-DhcpServerInDC.md)
Retrieves the list of authorized computers running the Dynamic Host Configuration Protocol (DHCP) server service from Active Directory (AD).

### [Get-DhcpServerSetting](./Get-DhcpServerSetting.md)
Gets the configuration parameters of the database of the Dynamic Host Configuration Protocol (DHCP) server service.

### [Get-DhcpServerv4Binding](./Get-DhcpServerv4Binding.md)
Gets all of the IPv4 interfaces on the computer to which the Dynamic Host Configuration Protocol (DHCP) server service is bound.

### [Get-DhcpServerv4Class](./Get-DhcpServerv4Class.md)
Retrieves an IPv4 vendor or user class from the Dynamic Host Configuration Protocol (DHCP) server service.

### [Get-DhcpServerv4DnsSetting](./Get-DhcpServerv4DnsSetting.md)
Gets the DNS settings configured on the Dynamic Host Configuration Protocol (DHCP) server service for a specific scope, reservation, or server level.

### [Get-DhcpServerv4ExclusionRange](./Get-DhcpServerv4ExclusionRange.md)
Returns the IPv4 address ranges excluded from the specified scope identifiers (IDs).

### [Get-DhcpServerv4Failover](./Get-DhcpServerv4Failover.md)
Gets the failover relationships configured on the Dynamic Host Configuration Protocol (DHCP) server service for the specific failover relationship name.

### [Get-DhcpServerv4Filter](./Get-DhcpServerv4Filter.md)
Gets the list of all MAC addresses from the allow list or the deny list on the Dynamic Host Configuration Protocol (DHCP) server service.

### [Get-DhcpServerv4FilterList](./Get-DhcpServerv4FilterList.md)
Gets the enabled state of the allow filter list and deny filter list set on the Dynamic Host Configuration Protocol (DHCP) server service.

### [Get-DhcpServerv4FreeIPAddress](./Get-DhcpServerv4FreeIPAddress.md)
Gets one or more free, or unassigned, IPv4 Addresses from the specified scope.

### [Get-DhcpServerv4Lease](./Get-DhcpServerv4Lease.md)
Gets one or more lease records from the Dynamic Host Configuration Protocol (DHCP) server service.

### [Get-DhcpServerv4MulticastExclusionRange](./Get-DhcpServerv4MulticastExclusionRange.md)
Retrieves the exclusion range for a specified multicast scope.

### [Get-DhcpServerv4MulticastLease](./Get-DhcpServerv4MulticastLease.md)
Retrieves multicast leases for a specified scope name.

### [Get-DhcpServerv4MulticastScope](./Get-DhcpServerv4MulticastScope.md)
Gets multicast scope objects.

### [Get-DhcpServerv4MulticastScopeStatistics](./Get-DhcpServerv4MulticastScopeStatistics.md)
Gets multicast scope statistics.

### [Get-DhcpServerv4OptionDefinition](./Get-DhcpServerv4OptionDefinition.md)
Gets the DHCPv4 option definition for the specified option identifiers (IDs).

### [Get-DhcpServerv4OptionValue](./Get-DhcpServerv4OptionValue.md)
Returns the IPv4 option Values for one or more IPv4 options at the server, scope or reservation level.

### [Get-DhcpServerv4Policy](./Get-DhcpServerv4Policy.md)
Gets one or more policies at the server level or the scope level.

### [Get-DhcpServerv4PolicyIPRange](./Get-DhcpServerv4PolicyIPRange.md)
Gets one or more IP ranges from a policy in the specified scope.

### [Get-DhcpServerv4Reservation](./Get-DhcpServerv4Reservation.md)
Gets one or more IPv4 reservations for the specified IP addresses or client identifiers (IDs).

### [Get-DhcpServerv4Scope](./Get-DhcpServerv4Scope.md)
Returns the IPv4 scope configuration of the specified scopes.

### [Get-DhcpServerv4ScopeStatistics](./Get-DhcpServerv4ScopeStatistics.md)
Gets the IPv4 scope statistics corresponding to the IPv4 scope identifiers (IDs) specified for a Dynamic Host Configuration Protocol (DHCP) server service.

### [Get-DhcpServerv4Statistics](./Get-DhcpServerv4Statistics.md)
Gets Dynamic Host Configuration Protocol (DHCP) server service statistics for IPv4.

### [Get-DhcpServerv4Superscope](./Get-DhcpServerv4Superscope.md)
Gets the configuration for the specified superscope.

### [Get-DhcpServerv4SuperscopeStatistics](./Get-DhcpServerv4SuperscopeStatistics.md)
Returns statistics for superscopes.

### [Get-DhcpServerv6Binding](./Get-DhcpServerv6Binding.md)
Returns the IPv6 interfaces to which the Dynamic Host Configuration Protocol (DHCP) server service is bound.

### [Get-DhcpServerv6Class](./Get-DhcpServerv6Class.md)
Gets the IPv6 vendor or user class from the Dynamic Host Configuration Protocol (DHCP) server service.

### [Get-DhcpServerv6DnsSetting](./Get-DhcpServerv6DnsSetting.md)
Gets the DNS settings configured on the Dynamic Host Configuration Protocol (DHCP) server service for a specific scope, reservation, or server-wide.

### [Get-DhcpServerv6ExclusionRange](./Get-DhcpServerv6ExclusionRange.md)
Gets the IPv6 address ranges excluded from the specified IPv6 subnet prefix.

### [Get-DhcpServerv6FreeIPAddress](./Get-DhcpServerv6FreeIPAddress.md)
Gets one or more free, or unassigned, IPv6 addresses from the specified scope.

### [Get-DhcpServerv6Lease](./Get-DhcpServerv6Lease.md)
Gets one or more IPv6 lease records from the Dynamic Host Configuration Protocol (DHCP) server service.

### [Get-DhcpServerv6OptionDefinition](./Get-DhcpServerv6OptionDefinition.md)
Gets the option definition for the option identified by the option identifier (ID).

### [Get-DhcpServerv6OptionValue](./Get-DhcpServerv6OptionValue.md)
Returns the IPv6 option values for one or more IPv6 options either for a specific reserved IP, scope or, server level.

### [Get-DhcpServerv6Reservation](./Get-DhcpServerv6Reservation.md)
Returns the reserved IPv6 addresses on the Dynamic Host Configuration Protocol (DHCP) server service.

### [Get-DhcpServerv6Scope](./Get-DhcpServerv6Scope.md)
Gets the scope information for the specified IPv6 prefixes on the Dynamic Host Configuration Protocol (DHCP) server service.

### [Get-DhcpServerv6ScopeStatistics](./Get-DhcpServerv6ScopeStatistics.md)
Gets the IPv6 prefix statistics that correspond to the IPv6 prefix specified for a Dynamic Host Configuration Protocol (DHCP) server service.

### [Get-DhcpServerv6StatelessStatistics](./Get-DhcpServerv6StatelessStatistics.md)
Gets a list of IPv6 subnet prefixes which have stateless clients and the number of addresses in use in each of the subnets.

### [Get-DhcpServerv6StatelessStore](./Get-DhcpServerv6StatelessStore.md)
Gets the properties of IPv6 stateless store for the specified IPv6 subnet.

### [Get-DhcpServerv6Statistics](./Get-DhcpServerv6Statistics.md)
Gets the Dynamic Host Configuration Protocol (DHCP) server service statistics for IPv6.

### [Get-DhcpServerVersion](./Get-DhcpServerVersion.md)
Gets the version of the Dynamic Host Configuration Protocol (DHCP) server service.

### [Import-DhcpServer](./Import-DhcpServer.md)
Imports the Dynamic Host Configuration Protocol (DHCP) server service configuration, and optionally lease data, from the specified file.

### [Invoke-DhcpServerv4FailoverReplication](./Invoke-DhcpServerv4FailoverReplication.md)
Replicates scope configuration between failover partner Dynamic Host Configuration Protocol (DHCP) server services.

### [Remove-DhcpServerDnsCredential](./Remove-DhcpServerDnsCredential.md)
Removes the credential that the DHCP Server service uses to register or deregister client records on a DNS server.

### [Remove-DhcpServerInDC](./Remove-DhcpServerInDC.md)
Deletes the specified Dynamic Host Configuration Protocol (DHCP) server service from the list of authorized DHCP server services in Active Directory (AD).

### [Remove-DhcpServerv4Class](./Remove-DhcpServerv4Class.md)
Deletes the IPv4 vendor class or user class from a Dynamic Host Configuration Protocol (DHCP) server service.

### [Remove-DhcpServerv4ExclusionRange](./Remove-DhcpServerv4ExclusionRange.md)
Deletes a range of IPv4 addresses that were previously excluded from an IPv4 scope.

### [Remove-DhcpServerv4Failover](./Remove-DhcpServerv4Failover.md)
Removes one or more specified failover relationships.

### [Remove-DhcpServerv4FailoverScope](./Remove-DhcpServerv4FailoverScope.md)
Removes the specified scopes from the failover relationship.

### [Remove-DhcpServerv4Filter](./Remove-DhcpServerv4Filter.md)
Deletes the specified MAC address or MAC address pattern from the allow list or the deny list of the Dynamic Host Configuration Protocol (DHCP) server service.

### [Remove-DhcpServerv4Lease](./Remove-DhcpServerv4Lease.md)
Deletes the specified IPv4 address lease record from the Dynamic Host Configuration Protocol (DHCP) server service.

### [Remove-DhcpServerv4MulticastExclusionRange](./Remove-DhcpServerv4MulticastExclusionRange.md)
Removes a range of addresses previously excluded from a multicast scope.

### [Remove-DhcpServerv4MulticastLease](./Remove-DhcpServerv4MulticastLease.md)
Removes one or more multicast scope leases for a specified multicast scope or IP address.

### [Remove-DhcpServerv4MulticastScope](./Remove-DhcpServerv4MulticastScope.md)
Removes multicast scopes.

### [Remove-DhcpServerv4OptionDefinition](./Remove-DhcpServerv4OptionDefinition.md)
Deletes one or more IPv4 option definitions from a Dynamic Host Configuration Protocol (DHCP) server service.

### [Remove-DhcpServerv4OptionValue](./Remove-DhcpServerv4OptionValue.md)
Deletes one or more IPv4 option values at the server, scope or reservation level, either for the standard IPv4 options or for the specified vendor or user class.

### [Remove-DhcpServerv4Policy](./Remove-DhcpServerv4Policy.md)
Deletes one or more specified IPv4 policies either at the server level or the specified scope level.

### [Remove-DhcpServerv4PolicyIPRange](./Remove-DhcpServerv4PolicyIPRange.md)
Deletes an IP range from an existing policy at the scope level.

### [Remove-DhcpServerv4Reservation](./Remove-DhcpServerv4Reservation.md)
Deletes the IPv4 Reservation from the specified scope.

### [Remove-DhcpServerv4Scope](./Remove-DhcpServerv4Scope.md)
Deletes the specified IPv4 scopes from the  Dynamic Host Configuration Protocol (DHCP) server service.

### [Remove-DhcpServerv4Superscope](./Remove-DhcpServerv4Superscope.md)
Removes one or more specified scopes from a superscope.

### [Remove-DhcpServerv6Class](./Remove-DhcpServerv6Class.md)
Deletes the specified IPv6 vendor class or user class from a Dynamic Host Configuration Protocol (DHCP) server service.

### [Remove-DhcpServerv6ExclusionRange](./Remove-DhcpServerv6ExclusionRange.md)
Deletes a range of IPv6 addresses previously excluded from an IPv6 scope.

### [Remove-DhcpServerv6Lease](./Remove-DhcpServerv6Lease.md)
Deletes one or more IPv6 lease records from the Dynamic Host Configuration Protocol (DHCP) server service.

### [Remove-DhcpServerv6OptionDefinition](./Remove-DhcpServerv6OptionDefinition.md)
Deletes one or more IPv6 option definitions from the Dynamic Host Configuration Protocol (DHCP) server service.

### [Remove-DhcpServerv6OptionValue](./Remove-DhcpServerv6OptionValue.md)
Deletes one or more DHCPv6 option values set at the reservation level, scope level, or server level, either for the standard IPv6 options or for a specified vendor class.

### [Remove-DhcpServerv6Reservation](./Remove-DhcpServerv6Reservation.md)
Deletes one or more IPv6 reservations from the specified scope.

### [Remove-DhcpServerv6Scope](./Remove-DhcpServerv6Scope.md)
Deletes the IPv6 Scopes from the Dynamic Host Configuration Protocol (DHCP) server service corresponding to the specified prefixes.

### [Rename-DhcpServerv4Superscope](./Rename-DhcpServerv4Superscope.md)
Renames a superscope.

### [Repair-DhcpServerv4IPRecord](./Repair-DhcpServerv4IPRecord.md)
Reconciles inconsistent lease records in the DHCP database.

### [Restore-DhcpServer](./Restore-DhcpServer.md)
Restores the database of the Dynamic Host Configuration Protocol (DHCP) server service from the specified location.

### [Set-DhcpServerAuditLog](./Set-DhcpServerAuditLog.md)
Sets the Dynamic Host Configuration Protocol (DHCP) server service audit log configuration on the DHCP server service running on the computer.

### [Set-DhcpServerDatabase](./Set-DhcpServerDatabase.md)
Modifies one or more configuration parameters of the database of the Dynamic Host Configuration Protocol (DHCP) server service.

### [Set-DhcpServerDnsCredential](./Set-DhcpServerDnsCredential.md)
Sets credentials that the DHCP Server service uses to register or deregister client records on a DNS server.

### [Set-DhcpServerSetting](./Set-DhcpServerSetting.md)
Sets one or more server level configuration parameters for the Dynamic Host Configuration Protocol (DHCP) server service.

### [Set-DhcpServerv4Binding](./Set-DhcpServerv4Binding.md)
Sets the binding state of specified IPv4 interface for the Dynamic Host Configuration Protocol (DHCP) server service running on the specified computer.

### [Set-DhcpServerv4Class](./Set-DhcpServerv4Class.md)
Modifies an IPv4 vendor class or user class on the Dynamic Host Configuration Protocol (DHCP) server service with the specified parameters.

### [Set-DhcpServerv4DnsSetting](./Set-DhcpServerv4DnsSetting.md)
Configures how the Dynamic Host Configuration Protocol (DHCP) server service updates the DNS server with the client-related information.

### [Set-DhcpServerv4Failover](./Set-DhcpServerv4Failover.md)
Modifies the properties of an existing failover relationship.

### [Set-DhcpServerv4FilterList](./Set-DhcpServerv4FilterList.md)
Sets the enabled state for the allow and the deny MAC address filter lists on the Dynamic Host Configuration Protocol (DHCP) server service.

### [Set-DhcpServerv4MulticastScope](./Set-DhcpServerv4MulticastScope.md)
Modifies the properties of a multicast scope.

### [Set-DhcpServerv4OptionDefinition](./Set-DhcpServerv4OptionDefinition.md)
Modifies the properties of an existing IPv4 option definition.

### [Set-DhcpServerv4OptionValue](./Set-DhcpServerv4OptionValue.md)
Sets an IPv4 option value at the server, scope, or reservation level.

### [Set-DhcpServerv4Policy](./Set-DhcpServerv4Policy.md)
Sets the properties of an existing policy either at the server level or at the specified scope level.

### [Set-DhcpServerv4Reservation](./Set-DhcpServerv4Reservation.md)
Modifies the properties of an IPv4 reservation.

### [Set-DhcpServerv4Scope](./Set-DhcpServerv4Scope.md)
Sets the properties of an existing IPv4 scope on the Dynamic Host Configuration Protocol (DHCP) server service.

### [Set-DhcpServerv6Binding](./Set-DhcpServerv6Binding.md)
Sets the binding state for the specified IPv6 interface of the Dynamic Host Configuration Protocol (DHCP) server service on the computer.

### [Set-DhcpServerv6Class](./Set-DhcpServerv6Class.md)
Modifies the properties of an IPv6 vendor or user class on the Dynamic Host Configuration Protocol (DHCP) server service.

### [Set-DhcpServerv6DnsSetting](./Set-DhcpServerv6DnsSetting.md)
Configures how the Dynamic Host Configuration Protocol (DHCP) server service updates the DNS server with the client-related information.

### [Set-DhcpServerv6OptionDefinition](./Set-DhcpServerv6OptionDefinition.md)
Modifies the properties of an existing DHCPv6 option definition.

### [Set-DhcpServerv6OptionValue](./Set-DhcpServerv6OptionValue.md)
Sets an IPv6 option value at the server, scope, or reservation level.

### [Set-DhcpServerv6Reservation](./Set-DhcpServerv6Reservation.md)
Modifies the properties of the specified IPv6 reservation.

### [Set-DhcpServerv6Scope](./Set-DhcpServerv6Scope.md)
Modifies the properties of the IPv6 scope on the Dynamic Host Configuration Protocol (DHCP) server service.

### [Set-DhcpServerv6StatelessStore](./Set-DhcpServerv6StatelessStore.md)
Sets the properties of IPv6 stateless store for the specified IPv6 prefix.

