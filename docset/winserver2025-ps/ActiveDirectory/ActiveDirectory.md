---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
Download Help Link: https://aka.ms/winsvr-2025-pshelp
Help Version: 4.0.6.1
Locale: en-US
Module Guid: 43c15630-959c-49e4-a977-758c5cc93408
Module Name: ActiveDirectory
ms.date: 12/27/2016
title: ActiveDirectory
---

# ActiveDirectory Module
## Description
The Active Directory module for Windows PowerShell is a PowerShell module that consolidates a group of cmdlets. You can use these cmdlets to manage your Active Directory domains, Active Directory Lightweight Directory Services (AD LDS) configuration sets, and Active Directory Database Mounting Tool instances in a single, self-contained package.

If you don't have the Active Directory module installed on your machine, you need to download the correct Remote Server Administration Tools (RSAT) package for your OS.  If you're running Windows 7, you will also need to run the `import-module ActiveDirectory` command from an elevated PowerShell prompt. For more detail, see [RSAT for Windows operating systems](https://support.microsoft.com/help/2693643/remote-server-administration-tools-rsat-for-windows-operating-systems). Starting with Windows 10 October 2018 Update, RSAT is included as a set of Features on Demand right from Windows 10. Now, instead of downloading an RSAT package you can just go to Manage optional features in Settings and click Add a feature to see the list of available RSAT tools. Select and install the specific RSAT tools you need. To see installation progress, click the Back button to view status on the Manage optional features page.

If you want to use this module in PowerShell 7, see [PowerShell 7 module compatibility](/powershell/scripting/whats-new/module-compatibility).

## ActiveDirectory Cmdlets
### [Add-ADCentralAccessPolicyMember](./Add-ADCentralAccessPolicyMember.md)
Adds central access rules to a central access policy in Active Directory.

### [Add-ADComputerServiceAccount](./Add-ADComputerServiceAccount.md)
Adds one or more service accounts to an Active Directory computer.

### [Add-ADDomainControllerPasswordReplicationPolicy](./Add-ADDomainControllerPasswordReplicationPolicy.md)
Adds users, computers, and groups to the allowed or denied list of a read-only domain controller password replication policy.

### [Add-ADFineGrainedPasswordPolicySubject](./Add-ADFineGrainedPasswordPolicySubject.md)
Applies a fine-grained password policy to one or more users and groups.

### [Add-ADGroupMember](./Add-ADGroupMember.md)
Adds one or more members to an Active Directory group.

### [Add-ADPrincipalGroupMembership](./Add-ADPrincipalGroupMembership.md)
Adds a member to one or more Active Directory groups.

### [Add-ADResourcePropertyListMember](./Add-ADResourcePropertyListMember.md)
Adds one or more resource properties to a resource property list in Active Directory.

### [Clear-ADAccountExpiration](./Clear-ADAccountExpiration.md)
Clears the expiration date for an Active Directory account.

### [Clear-ADClaimTransformLink](./Clear-ADClaimTransformLink.md)
Removes a claims transformation from being applied to one or more cross-forest trust relationships in Active Directory.

### [Complete-ADServiceAccountMigration](./Complete-ADServiceAccountMigration.md)
Completes the migration process of a service account to a delegated managed service account.

### [Disable-ADAccount](./Disable-ADAccount.md)
Disables an Active Directory account.

### [Disable-ADOptionalFeature](./Disable-ADOptionalFeature.md)
Disables an Active Directory optional feature.

### [Enable-ADAccount](./Enable-ADAccount.md)
Enables an Active Directory account.

### [Enable-ADOptionalFeature](./Enable-ADOptionalFeature.md)
Enables an Active Directory optional feature.

### [Get-ADAccountAuthorizationGroup](./Get-ADAccountAuthorizationGroup.md)
Gets the accounts token group information.

### [Get-ADAccountResultantPasswordReplicationPolicy](./Get-ADAccountResultantPasswordReplicationPolicy.md)
Gets the resultant password replication policy for an Active Directory account.

### [Get-ADAuthenticationPolicy](./Get-ADAuthenticationPolicy.md)
Gets one or more Active Directory Domain Services authentication policies.

### [Get-ADAuthenticationPolicySilo](./Get-ADAuthenticationPolicySilo.md)
Gets one or more Active Directory Domain Services authentication policy silos.

### [Get-ADCentralAccessPolicy](./Get-ADCentralAccessPolicy.md)
Retrieves central access policies from Active Directory.

### [Get-ADCentralAccessRule](./Get-ADCentralAccessRule.md)
Retrieves central access rules from Active Directory.

### [Get-ADClaimTransformPolicy](./Get-ADClaimTransformPolicy.md)
Returns one or more Active Directory claim transform objects based on a specified filter.

### [Get-ADClaimType](./Get-ADClaimType.md)
Returns a claim type from Active Directory.

### [Get-ADComputer](./Get-ADComputer.md)
Gets one or more Active Directory computers.

### [Get-ADComputerServiceAccount](./Get-ADComputerServiceAccount.md)
Gets the service accounts hosted by a computer.

### [Get-ADDCCloningExcludedApplicationList](./Get-ADDCCloningExcludedApplicationList.md)
Gets a list of installed programs and services present on this domain controller that are not in the default or user defined inclusion list.

### [Get-ADDefaultDomainPasswordPolicy](./Get-ADDefaultDomainPasswordPolicy.md)
Gets the default password policy for an Active Directory domain.

### [Get-ADDomain](./Get-ADDomain.md)
Gets an Active Directory domain.

### [Get-ADDomainController](./Get-ADDomainController.md)
Gets one or more Active Directory domain controllers based on discoverable services criteria, search parameters or by providing a domain controller identifier, such as the NetBIOS name.

### [Get-ADDomainControllerPasswordReplicationPolicy](./Get-ADDomainControllerPasswordReplicationPolicy.md)
Gets the members of the allowed list or denied list of a read-only domain controller's password replication policy.

### [Get-ADDomainControllerPasswordReplicationPolicyUsage](./Get-ADDomainControllerPasswordReplicationPolicyUsage.md)
Gets the Active Directory accounts that are authenticated by a read-only domain controller or that are in the revealed list of the domain controller.

### [Get-ADFineGrainedPasswordPolicy](./Get-ADFineGrainedPasswordPolicy.md)
Gets one or more Active Directory fine-grained password policies.

### [Get-ADFineGrainedPasswordPolicySubject](./Get-ADFineGrainedPasswordPolicySubject.md)
Gets the users and groups to which a fine-grained password policy is applied.

### [Get-ADForest](./Get-ADForest.md)
Gets an Active Directory forest.

### [Get-ADGroup](./Get-ADGroup.md)
Gets one or more Active Directory groups.

### [Get-ADGroupMember](./Get-ADGroupMember.md)
Gets the members of an Active Directory group.

### [Get-ADObject](./Get-ADObject.md)
Gets one or more Active Directory objects.

### [Get-ADOptionalFeature](./Get-ADOptionalFeature.md)
Gets one or more Active Directory optional features.

### [Get-ADOrganizationalUnit](./Get-ADOrganizationalUnit.md)
Gets one or more Active Directory organizational units.

### [Get-ADPrincipalGroupMembership](./Get-ADPrincipalGroupMembership.md)
Gets the Active Directory groups that have a specified user, computer, group, or service account.

### [Get-ADReplicationAttributeMetadata](./Get-ADReplicationAttributeMetadata.md)
Gets the replication metadata for one or more Active Directory replication partners.

### [Get-ADReplicationConnection](./Get-ADReplicationConnection.md)
Returns a specific Active Directory replication connection or a set of AD replication connection objects based on a specified filter.

### [Get-ADReplicationFailure](./Get-ADReplicationFailure.md)
Returns a collection of data describing an Active Directory replication failure.

### [Get-ADReplicationPartnerMetadata](./Get-ADReplicationPartnerMetadata.md)
Returns the replication metadata for a set of one or more replication partners.

### [Get-ADReplicationQueueOperation](./Get-ADReplicationQueueOperation.md)
Returns the contents of the replication queue for a specified server.

### [Get-ADReplicationSite](./Get-ADReplicationSite.md)
Returns a specific Active Directory replication site or a set of replication site objects based on a specified filter.

### [Get-ADReplicationSiteLink](./Get-ADReplicationSiteLink.md)
Returns a specific Active Directory site link or a set of site links based on a specified filter.

### [Get-ADReplicationSiteLinkBridge](./Get-ADReplicationSiteLinkBridge.md)
Gets a specific Active Directory site link bridge or a set of site link bridge objects based on a specified filter.

### [Get-ADReplicationSubnet](./Get-ADReplicationSubnet.md)
Gets one or more Active Directory subnets.

### [Get-ADReplicationUpToDatenessVectorTable](./Get-ADReplicationUpToDatenessVectorTable.md)
Displays the highest Update Sequence Number (USN) for the specified domain controller.

### [Get-ADResourceProperty](./Get-ADResourceProperty.md)
Gets one or more resource properties.

### [Get-ADResourcePropertyList](./Get-ADResourcePropertyList.md)
Gets resource property lists from Active Directory.

### [Get-ADResourcePropertyValueType](./Get-ADResourcePropertyValueType.md)
Gets a resource property value type from Active Directory.

### [Get-ADRootDSE](./Get-ADRootDSE.md)
Gets the root of a directory server information tree.

### [Get-ADServiceAccount](./Get-ADServiceAccount.md)
Gets one or more Active Directory managed service accounts or group managed service accounts.

### [Get-ADTrust](./Get-ADTrust.md)
Gets all trusted domain objects in the directory.

### [Get-ADUser](./Get-ADUser.md)
Gets one or more Active Directory users.

### [Get-ADUserResultantPasswordPolicy](./Get-ADUserResultantPasswordPolicy.md)
Gets the resultant password policy for a user.

### [Grant-ADAuthenticationPolicySiloAccess](./Grant-ADAuthenticationPolicySiloAccess.md)
Grants permission to join an authentication policy silo.

### [Install-ADServiceAccount](./Install-ADServiceAccount.md)
Installs an Active Directory managed service account on a computer or caches a group managed service account on a computer.

### [Move-ADDirectoryServer](./Move-ADDirectoryServer.md)
Moves a directory server in Active Directory to a new site.

### [Move-ADDirectoryServerOperationMasterRole](./Move-ADDirectoryServerOperationMasterRole.md)
Moves operation master roles to an Active Directory directory server.

### [Move-ADObject](./Move-ADObject.md)
Moves an Active Directory object or a container of objects to a different container or domain.

### [New-ADAuthenticationPolicy](./New-ADAuthenticationPolicy.md)
Creates an Active Directory Domain Services authentication policy object.

### [New-ADAuthenticationPolicySilo](./New-ADAuthenticationPolicySilo.md)
Creates an Active Directory Domain Services authentication policy silo object.

### [New-ADCentralAccessPolicy](./New-ADCentralAccessPolicy.md)
Creates a new central access policy in Active Directory containing a set of central access rules.

### [New-ADCentralAccessRule](./New-ADCentralAccessRule.md)
Creates a central access rule in Active Directory.

### [New-ADClaimTransformPolicy](./New-ADClaimTransformPolicy.md)
Creates a new claim transformation policy object in Active Directory.

### [New-ADClaimType](./New-ADClaimType.md)
Creates a new claim type in Active Directory.

### [New-ADComputer](./New-ADComputer.md)
Creates a new Active Directory computer object.

### [New-ADDCCloneConfigFile](./New-ADDCCloneConfigFile.md)
Performs prerequisite checks for cloning a domain controller and generates a clone configuration file if all checks succeed.

### [New-ADFineGrainedPasswordPolicy](./New-ADFineGrainedPasswordPolicy.md)
Creates a new Active Directory fine-grained password policy.

### [New-ADGroup](./New-ADGroup.md)
Creates an Active Directory group.

### [New-ADObject](./New-ADObject.md)
Creates an Active Directory object.

### [New-ADOrganizationalUnit](./New-ADOrganizationalUnit.md)
Creates an Active Directory organizational unit.

### [New-ADReplicationSite](./New-ADReplicationSite.md)
Creates an Active Directory replication site in the directory.

### [New-ADReplicationSiteLink](./New-ADReplicationSiteLink.md)
Creates a new Active Directory site link for in managing replication.

### [New-ADReplicationSiteLinkBridge](./New-ADReplicationSiteLinkBridge.md)
Creates a site link bridge in Active Directory for replication.

### [New-ADReplicationSubnet](./New-ADReplicationSubnet.md)
Creates an Active Directory replication subnet object.

### [New-ADResourceProperty](./New-ADResourceProperty.md)
Creates a resource property in Active Directory.

### [New-ADResourcePropertyList](./New-ADResourcePropertyList.md)
Creates a resource property list in Active Directory.

### [New-ADServiceAccount](./New-ADServiceAccount.md)
Creates a new Active Directory managed service account or group managed service account object.

### [New-ADUser](./New-ADUser.md)
Creates an Active Directory user.

### [Remove-ADAuthenticationPolicy](./Remove-ADAuthenticationPolicy.md)
Removes an Active Directory Domain Services authentication policy object.

### [Remove-ADAuthenticationPolicySilo](./Remove-ADAuthenticationPolicySilo.md)
Removes an Active Directory Domain Services authentication policy silo object.

### [Remove-ADCentralAccessPolicy](./Remove-ADCentralAccessPolicy.md)
Removes a central access policy from Active Directory.

### [Remove-ADCentralAccessPolicyMember](./Remove-ADCentralAccessPolicyMember.md)
Removes central access rules from a central access policy in Active Directory.

### [Remove-ADCentralAccessRule](./Remove-ADCentralAccessRule.md)
Removes a central access rule from Active Directory.

### [Remove-ADClaimTransformPolicy](./Remove-ADClaimTransformPolicy.md)
Removes a claim transformation policy object from Active Directory.

### [Remove-ADClaimType](./Remove-ADClaimType.md)
Removes a claim type from Active Directory.

### [Remove-ADComputer](./Remove-ADComputer.md)
Removes an Active Directory computer.

### [Remove-ADComputerServiceAccount](./Remove-ADComputerServiceAccount.md)
Removes one or more service accounts from a computer.

### [Remove-ADDomainControllerPasswordReplicationPolicy](./Remove-ADDomainControllerPasswordReplicationPolicy.md)
Removes users, computers, and groups from the allowed or denied list of a read-only domain controller password replication policy.

### [Remove-ADFineGrainedPasswordPolicy](./Remove-ADFineGrainedPasswordPolicy.md)
Removes an Active Directory fine-grained password policy.

### [Remove-ADFineGrainedPasswordPolicySubject](./Remove-ADFineGrainedPasswordPolicySubject.md)
Removes one or more users from a fine-grained password policy.

### [Remove-ADGroup](./Remove-ADGroup.md)
Removes an Active Directory group.

### [Remove-ADGroupMember](./Remove-ADGroupMember.md)
Removes one or more members from an Active Directory group.

### [Remove-ADObject](./Remove-ADObject.md)
Removes an Active Directory object.

### [Remove-ADOrganizationalUnit](./Remove-ADOrganizationalUnit.md)
Removes an Active Directory organizational unit.

### [Remove-ADPrincipalGroupMembership](./Remove-ADPrincipalGroupMembership.md)
Removes a member from one or more Active Directory groups.

### [Remove-ADReplicationSite](./Remove-ADReplicationSite.md)
Deletes the specified replication site object from Active Directory.

### [Remove-ADReplicationSiteLink](./Remove-ADReplicationSiteLink.md)
Deletes an Active Directory site link used to manage replication.

### [Remove-ADReplicationSiteLinkBridge](./Remove-ADReplicationSiteLinkBridge.md)
Deletes a replication site link bridge from Active Directory.

### [Remove-ADReplicationSubnet](./Remove-ADReplicationSubnet.md)
Deletes the specified Active Directory replication subnet object from the directory.

### [Remove-ADResourceProperty](./Remove-ADResourceProperty.md)
Removes a resource property from Active Directory.

### [Remove-ADResourcePropertyList](./Remove-ADResourcePropertyList.md)
Removes one or more resource property lists from Active Directory.

### [Remove-ADResourcePropertyListMember](./Remove-ADResourcePropertyListMember.md)
Removes one or more resource properties from a resource property list in Active Directory.

### [Remove-ADServiceAccount](./Remove-ADServiceAccount.md)
Removes an Active Directory managed service account or group managed service account object.

### [Remove-ADUser](./Remove-ADUser.md)
Removes an Active Directory user.

### [Rename-ADObject](./Rename-ADObject.md)
Changes the name of an Active Directory object.

### [Reset-ADServiceAccountMigration](./Reset-ADServiceAccountMigration.md)
Resets and unlinks the delegated managed service account from the user account.

### [Reset-ADServiceAccountPassword](./Reset-ADServiceAccountPassword.md)
Resets the password for a standalone managed service account.

### [Restore-ADObject](./Restore-ADObject.md)
Restores an Active Directory object.

### [Revoke-ADAuthenticationPolicySiloAccess](./Revoke-ADAuthenticationPolicySiloAccess.md)
Revokes membership in an authentication policy silo for the specified account.

### [Search-ADAccount](./Search-ADAccount.md)
Gets Active Directory user, computer, or service accounts.

### [Set-ADAccountAuthenticationPolicySilo](./Set-ADAccountAuthenticationPolicySilo.md)
Modifies the authentication policy or authentication policy silo of an account.

### [Set-ADAccountControl](./Set-ADAccountControl.md)
Modifies user account control (UAC) values for an Active Directory account.

### [Set-ADAccountExpiration](./Set-ADAccountExpiration.md)
Sets the expiration date for an Active Directory account.

### [Set-ADAccountPassword](./Set-ADAccountPassword.md)
Modifies the password of an Active Directory account.

### [Set-ADAuthenticationPolicy](./Set-ADAuthenticationPolicy.md)
Modifies an Active Directory Domain Services authentication policy object.

### [Set-ADAuthenticationPolicySilo](./Set-ADAuthenticationPolicySilo.md)
Modifies an Active Directory Domain Services authentication policy silo object.

### [Set-ADCentralAccessPolicy](./Set-ADCentralAccessPolicy.md)
Modifies a central access policy in Active Directory.

### [Set-ADCentralAccessRule](./Set-ADCentralAccessRule.md)
Modifies a central access rule in Active Directory.

### [Set-ADClaimTransformLink](./Set-ADClaimTransformLink.md)
Applies a claims transformation to one or more cross-forest trust relationships in Active Directory.

### [Set-ADClaimTransformPolicy](./Set-ADClaimTransformPolicy.md)
Sets the properties of a claims transformation policy in Active Directory.

### [Set-ADClaimType](./Set-ADClaimType.md)
Modify a claim type in Active Directory.

### [Set-ADComputer](./Set-ADComputer.md)
Modifies an Active Directory computer object.

### [Set-ADDefaultDomainPasswordPolicy](./Set-ADDefaultDomainPasswordPolicy.md)
Modifies the default password policy for an Active Directory domain.

### [Set-ADDomain](./Set-ADDomain.md)
Modifies an Active Directory domain.

### [Set-ADDomainMode](./Set-ADDomainMode.md)
Sets the domain mode for an Active Directory domain.

### [Set-ADFineGrainedPasswordPolicy](./Set-ADFineGrainedPasswordPolicy.md)
Modifies an Active Directory fine-grained password policy.

### [Set-ADForest](./Set-ADForest.md)
Modifies an Active Directory forest.

### [Set-ADForestMode](./Set-ADForestMode.md)
Sets the forest mode for an Active Directory forest.

### [Set-ADGroup](./Set-ADGroup.md)
Modifies an Active Directory group.

### [Set-ADObject](./Set-ADObject.md)
Modifies an Active Directory object.

### [Set-ADOrganizationalUnit](./Set-ADOrganizationalUnit.md)
Modifies an Active Directory organizational unit.

### [Set-ADReplicationConnection](./Set-ADReplicationConnection.md)
Sets properties on Active Directory replication connections.

### [Set-ADReplicationSite](./Set-ADReplicationSite.md)
Sets the replication properties for an Active Directory site.

### [Set-ADReplicationSiteLink](./Set-ADReplicationSiteLink.md)
Sets the properties for an Active Directory site link.

### [Set-ADReplicationSiteLinkBridge](./Set-ADReplicationSiteLinkBridge.md)
Sets the properties of a replication site link bridge in Active Directory.

### [Set-ADReplicationSubnet](./Set-ADReplicationSubnet.md)
Sets the properties of an Active Directory replication subnet object.

### [Set-ADResourceProperty](./Set-ADResourceProperty.md)
Modifies a resource property in Active Directory.

### [Set-ADResourcePropertyList](./Set-ADResourcePropertyList.md)
Modifies a resource property list in Active Directory.

### [Set-ADServiceAccount](./Set-ADServiceAccount.md)
Modifies an Active Directory managed service account or group managed service account object.

### [Set-ADUser](./Set-ADUser.md)
Modifies an Active Directory user.

### [Show-ADAuthenticationPolicyExpression](./Show-ADAuthenticationPolicyExpression.md)
Displays the Edit Access Control Conditions window update or create security descriptor definition language (SDDL) security descriptors.

### [Start-ADServiceAccountMigration](./Start-ADServiceAccountMigration.md)
Starts the migration of a user account to a delegated managed service account.

### [Sync-ADObject](./Sync-ADObject.md)
Replicates a single object between any two domain controllers that have partitions in common.

### [Test-ADServiceAccount](./Test-ADServiceAccount.md)
Tests a managed service account from a computer.

### [Undo-ADServiceAccountMigration](./Undo-ADServiceAccountMigration.md)
Reverts the migration phase of delegated managed service account to a user account.

### [Uninstall-ADServiceAccount](./Uninstall-ADServiceAccount.md)
Uninstalls an Active Directory managed service account from a computer or removes a cached group managed service account from a computer.

### [Unlock-ADAccount](./Unlock-ADAccount.md)
Unlocks an Active Directory account.
