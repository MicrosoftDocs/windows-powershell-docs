---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
Download Help Link: https://aka.ms/winsvr-2025-pshelp
Help Version: 4.0.3.1
Locale: en-US
Module Guid: 4b26ff51-7aee-4731-9cf7-508b82532cbf
Module Name: NetSecurity
ms.date: 12/27/2016
title: NetSecurity
---

# NetSecurity Module
## Description
This reference provides cmdlet descriptions and syntax for all Network Security cmdlets. It lists the cmdlets in alphabetical order based on the verb at the beginning of the cmdlet.

## NetSecurity Cmdlets
### [Copy-NetFirewallRule](./Copy-NetFirewallRule.md)
Copies an entire firewall rule, and associated filters, to the same or to a different policy store.

### [Copy-NetIPsecMainModeCryptoSet](./Copy-NetIPsecMainModeCryptoSet.md)
Copies an entire main mode cryptographic set to the same or to a different policy store.

### [Copy-NetIPsecMainModeRule](./Copy-NetIPsecMainModeRule.md)
Copies an entire main mode rule, and associated filters, to the same or to a different policy store.

### [Copy-NetIPsecPhase1AuthSet](./Copy-NetIPsecPhase1AuthSet.md)
Copies an entire phase 1 authentication set to the same or to a different policy store.

### [Copy-NetIPsecPhase2AuthSet](./Copy-NetIPsecPhase2AuthSet.md)
Copies an entire phase 2 authentication set to the same or to a different policy store.

### [Copy-NetIPsecQuickModeCryptoSet](./Copy-NetIPsecQuickModeCryptoSet.md)
Copies an entire quick mode cryptographic set to the same or to a different policy store.

### [Copy-NetIPsecRule](./Copy-NetIPsecRule.md)
Copies an entire IPsec rule, and the associated filters, to the same or to a different policy store.

### [Disable-NetFirewallRule](./Disable-NetFirewallRule.md)
Disables a firewall rule.

### [Disable-NetIPsecMainModeRule](./Disable-NetIPsecMainModeRule.md)
Disables a main mode rule.

### [Disable-NetIPsecRule](./Disable-NetIPsecRule.md)
Disables an IPsec rule.

### [Enable-NetFirewallRule](./Enable-NetFirewallRule.md)
Enables a previously disabled firewall rule.

### [Enable-NetIPsecMainModeRule](./Enable-NetIPsecMainModeRule.md)
Enables a previously disabled main mode rule.

### [Enable-NetIPsecRule](./Enable-NetIPsecRule.md)
Enables a previously disabled IPsec rule.

### [Find-NetIPsecRule](./Find-NetIPsecRule.md)
Gets IPsec rules that match specified criteria.

### [Get-DAPolicyChange](./Get-DAPolicyChange.md)
Gets a list of IP addresses that need to be added and deleted to an IPsec rule based on the differences detected between the IP addresses for the existing rule and the IP addresses derived from the input parameters, and creates a Windows PowerShell® script (.ps1) that updates the IPsec rule in the appropriate policy stores.

### [Get-NetFirewallAddressFilter](./Get-NetFirewallAddressFilter.md)
Retrieves address filter objects from the target computer.

### [Get-NetFirewallApplicationFilter](./Get-NetFirewallApplicationFilter.md)
Retrieves application filter objects from the target computer.

### [Get-NetFirewallDynamicKeywordAddress](Get-NetFirewallDynamicKeywordAddress.md)
Gets dynamic keyword addresses.

### [Get-NetFirewallInterfaceFilter](Get-NetFirewallInterfaceFilter.md)
Retrieves interface filter objects from the target computer.

### [Get-NetFirewallInterfaceTypeFilter](./Get-NetFirewallInterfaceTypeFilter.md)
Retrieves interface type filter objects from the target computer.

### [Get-NetFirewallPortFilter](./Get-NetFirewallPortFilter.md)
Retrieves port filter objects from the target computer.

### [Get-NetFirewallProfile](./Get-NetFirewallProfile.md)
Displays settings that apply to the per-profile configurations of the Windows Firewall with Advanced Security.

### [Get-NetFirewallRule](./Get-NetFirewallRule.md)
Retrieves firewall rules from the target computer.

### [Get-NetFirewallSecurityFilter](./Get-NetFirewallSecurityFilter.md)
Retrieves security filter objects from the target computer.

### [Get-NetFirewallServiceFilter](./Get-NetFirewallServiceFilter.md)
Retrieves service filter objects from the target computer.

### [Get-NetFirewallSetting](./Get-NetFirewallSetting.md)
Retrieves the global firewall settings of the target computer.

### [Get-NetIPsecDospSetting](./Get-NetIPsecDospSetting.md)
Retrieves IPsec DoS protection settings from the target computer.

### [Get-NetIPsecMainModeCryptoSet](./Get-NetIPsecMainModeCryptoSet.md)
Gets main mode cryptographic sets from the target computer.

### [Get-NetIPsecMainModeRule](./Get-NetIPsecMainModeRule.md)
Gets the IPsec main mode rules from the target computer.

### [Get-NetIPsecMainModeSA](./Get-NetIPsecMainModeSA.md)
Returns active main mode security associations (SA) from the target computer.

### [Get-NetIPsecPhase1AuthSet](./Get-NetIPsecPhase1AuthSet.md)
Gets a phase 1 authentication set from the target computer.

### [Get-NetIPsecPhase2AuthSet](./Get-NetIPsecPhase2AuthSet.md)
Gets a phase 2 authorization set from the target computer.

### [Get-NetIPsecQuickModeCryptoSet](./Get-NetIPsecQuickModeCryptoSet.md)
Gets a quick mode cryptographic set from the target computer.

### [Get-NetIPsecQuickModeSA](./Get-NetIPsecQuickModeSA.md)
Returns active quick mode security associations (SAs) from the target computer.

### [Get-NetIPsecRule](./Get-NetIPsecRule.md)
Gets an IPsec rule from the target computer.

### [New-NetFirewallDynamicKeywordAddress](New-NetFirewallDynamicKeywordAddress.md)
Creates a dynamic keyword address.

### [New-NetFirewallRule](New-NetFirewallRule.md)
Creates a new inbound or outbound firewall rule and adds the rule to the target computer.

### [New-NetIPsecAuthProposal](./New-NetIPsecAuthProposal.md)
Creates a main mode authentication proposal that specifies a suite of authentication protocols to offer in IPsec main mode negotiations with other computers.

### [New-NetIPsecDospSetting](./New-NetIPsecDospSetting.md)
Creates an IPsec DoS protection setting and adds the setting to the target computer.

### [New-NetIPsecMainModeCryptoProposal](./New-NetIPsecMainModeCryptoProposal.md)
Creates a main mode cryptographic proposal that specifies a suite of cryptographic protocols to offer in IPsec main mode negotiations with other computers.

### [New-NetIPsecMainModeCryptoSet](./New-NetIPsecMainModeCryptoSet.md)
Creates a main mode cryptographic set that contains suites of cryptographic protocols to offer in IPsec main mode negotiations with other computers.

### [New-NetIPsecMainModeRule](./New-NetIPsecMainModeRule.md)
Creates an IPsec main mode rule that tells the computer which peers require IPsec security associations (SAs) for securing network traffic, and how to negotiate those SAs.

### [New-NetIPsecPhase1AuthSet](./New-NetIPsecPhase1AuthSet.md)
Creates a phase 1 authentication set that specifies the methods offered for main mode first authentication during IPsec negotiations.

### [New-NetIPsecPhase2AuthSet](./New-NetIPsecPhase2AuthSet.md)
Creates a phase 2 authentication set that specifies the methods offered for second user authentication during IPsec negotiations.

### [New-NetIPsecQuickModeCryptoProposal](./New-NetIPsecQuickModeCryptoProposal.md)
Creates a quick mode cryptographic proposal that specifies a suite of cryptographic protocols to offer in IPsec quick mode negotiations with other computers.

### [New-NetIPsecQuickModeCryptoSet](./New-NetIPsecQuickModeCryptoSet.md)
Creates a quick mode cryptographic set that contains suites of cryptographic protocols to offer in IPsec quick mode negotiations with other computers.

### [New-NetIPsecRule](./New-NetIPsecRule.md)
Creates an IPsec rule that defines security requirements for network connections that match the specified criteria.

### [Open-NetGPO](./Open-NetGPO.md)
Creates a cached copy of the Group Policy Object (GPO) to modify locally.

### [Remove-NetFirewallDynamicKeywordAddress](Remove-NetFirewallDynamicKeywordAddress.md)
Removes dynamic keyword addresses.

### [Remove-NetFirewallRule](Remove-NetFirewallRule.md)
Deletes one or more firewall rules that match the specified criteria.

### [Remove-NetIPsecDospSetting](./Remove-NetIPsecDospSetting.md)
Deletes existing IPsec Dosp configurations.

### [Remove-NetIPsecMainModeCryptoSet](./Remove-NetIPsecMainModeCryptoSet.md)
Deletes any main mode cryptographic sets that match the specified criteria.

### [Remove-NetIPsecMainModeRule](./Remove-NetIPsecMainModeRule.md)
Deletes any main mode rules that match the specified criteria.

### [Remove-NetIPsecMainModeSA](./Remove-NetIPsecMainModeSA.md)
Removes an active main mode security association (SA).

### [Remove-NetIPsecPhase1AuthSet](./Remove-NetIPsecPhase1AuthSet.md)
Deletes all of the phase 1 authentication sets that match the specified criteria.

### [Remove-NetIPsecPhase2AuthSet](./Remove-NetIPsecPhase2AuthSet.md)
Deletes all of the phase 2 authentication sets that match the specified criteria.

### [Remove-NetIPsecQuickModeCryptoSet](./Remove-NetIPsecQuickModeCryptoSet.md)
Deletes all of the quick mode cryptographic sets that match the specified criteria.

### [Remove-NetIPsecQuickModeSA](./Remove-NetIPsecQuickModeSA.md)
Deletes an established quick mode security association (SA).

### [Remove-NetIPsecRule](./Remove-NetIPsecRule.md)
Defines security requirements for network connections that match the specified criteria.

### [Rename-NetFirewallRule](./Rename-NetFirewallRule.md)
Renames a single IPsec rule.

### [Rename-NetIPsecMainModeCryptoSet](./Rename-NetIPsecMainModeCryptoSet.md)
Renames a single main mode cryptographic set.

### [Rename-NetIPsecMainModeRule](./Rename-NetIPsecMainModeRule.md)
Renames a single main mode rule.

### [Rename-NetIPsecPhase1AuthSet](./Rename-NetIPsecPhase1AuthSet.md)
Renames a single phase 1 authentication set.

### [Rename-NetIPsecPhase2AuthSet](./Rename-NetIPsecPhase2AuthSet.md)
Renames a single phase 2 authentication set.

### [Rename-NetIPsecQuickModeCryptoSet](./Rename-NetIPsecQuickModeCryptoSet.md)
Renames a single quick mode cryptographic set.

### [Rename-NetIPsecRule](./Rename-NetIPsecRule.md)
Renames a single IPsec rule.

### [Save-NetGPO](./Save-NetGPO.md)
Applies the modified cached local Group Policy Object (GPO) to the actual GPO.

### [Set-NetFirewallAddressFilter](./Set-NetFirewallAddressFilter.md)
Modifies address filter objects, thereby modifying the local and remote address conditions of the firewall, IPsec, and main mode rules.

### [Set-NetFirewallApplicationFilter](./Set-NetFirewallApplicationFilter.md)
Modifies application filter objects, thereby modifying the program and package conditions of the firewall rules.

### [Set-NetFirewallInterfaceFilter](./Set-NetFirewallInterfaceFilter.md)
Modifies interface filter objects, thereby modifying the InterfaceAlias parameter values of the firewall or IPsec rules.

### [Set-NetFirewallInterfaceTypeFilter](./Set-NetFirewallInterfaceTypeFilter.md)
Modifies interface type filter objects, thereby modifying the interface type conditions of the firewall or IPsec rules.

### [Set-NetFirewallPortFilter](./Set-NetFirewallPortFilter.md)
Modifies port filter objects, thereby modifying the protocol and port conditions using the Protocol, LocalPort, RemotePort, IcmpType, and DynamicTransport parameters of the firewall or IPsec rules.

### [Set-NetFirewallProfile](./Set-NetFirewallProfile.md)
Configures settings that apply to the per-profile configurations of the Windows Firewall with Advanced Security.

### [Set-NetFirewallRule](./Set-NetFirewallRule.md)
Modifies existing firewall rules.

### [Set-NetFirewallSecurityFilter](./Set-NetFirewallSecurityFilter.md)
Modifies security filter objects, thereby modifying the Authentication, Encryption, OverrideBlockRules, LocalUser, RemoteUser, and RemoteMachine conditions of the firewall rules.

### [Set-NetFirewallServiceFilter](./Set-NetFirewallServiceFilter.md)
Modifies service filter objects, thereby modifying the service conditions of the firewall rules.

### [Set-NetFirewallSetting](./Set-NetFirewallSetting.md)
Modifies the global firewall settings of the target computer.

### [Set-NetIPsecDospSetting](./Set-NetIPsecDospSetting.md)
Modifies existing IPsec Dos protection settings.

### [Set-NetIPsecMainModeCryptoSet](./Set-NetIPsecMainModeCryptoSet.md)
Modifies existing main mode cryptographic sets.

### [Set-NetIPsecMainModeRule](./Set-NetIPsecMainModeRule.md)
Modifies existing main mode rules.

### [Set-NetIPsecPhase1AuthSet](./Set-NetIPsecPhase1AuthSet.md)
Modifies existing phase 1 authentication sets.

### [Set-NetIPsecPhase2AuthSet](./Set-NetIPsecPhase2AuthSet.md)
Modifies existing phase 2 authentication sets.

### [Set-NetIPsecQuickModeCryptoSet](./Set-NetIPsecQuickModeCryptoSet.md)
Modifies existing quick mode cryptographic sets.

### [Set-NetIPsecRule](./Set-NetIPsecRule.md)
Modifies existing IPsec rules.

### [Show-NetFirewallRule](./Show-NetFirewallRule.md)
Displays all of the existing IPsec rules and associated objects in a fully expanded view.

### [Show-NetIPsecRule](./Show-NetIPsecRule.md)
Displays all of the existing IPsec rules and associated objects in a fully expanded view.

### [Sync-NetIPsecRule](./Sync-NetIPsecRule.md)
Gets the list of IP addresses to be added and deleted to an IPsec rule based on the differences detected between the existing rule IP addresses and the specified IP addresses.

### [Update-NetFirewallDynamicKeywordAddress](Update-NetFirewallDynamicKeywordAddress.md)
Updates a dynamic keyword address.

### [Update-NetIPsecRule](Update-NetIPsecRule.md)
Updates an IPsec rule by adding or removing a set of IP addresses.


