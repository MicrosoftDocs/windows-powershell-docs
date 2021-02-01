---
external help file: Microsoft.DirectoryServices.Deployment.dll-Help.xml
Module Name: ADDSDeployment
online version: 
schema: 2.0.0
title: Test-ADDSDomainControllerUninstallation
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 4561C371-A381-4089-979A-69C64F4D1D5B
---

# Test-ADDSDomainControllerUninstallation

## SYNOPSIS
Runs the prerequisites (only) for uninstalling a domain controller in Active Directory.

## SYNTAX

### ADDSDomainControllerUninstall (Default)
```
Test-ADDSDomainControllerUninstallation [-LocalAdministratorPassword <SecureString>]
 [-Credential <PSCredential>] [-DemoteOperationMasterRole] [-DnsDelegationRemovalCredential <PSCredential>]
 [-IgnoreLastDCInDomainMismatch] [-IgnoreLastDnsServerForZone] [-LastDomainControllerInDomain]
 [-NoRebootOnCompletion] [-RemoveApplicationPartitions] [-RemoveDnsDelegation] [-RetainDCMetadata] [-Force]
 [<CommonParameters>]
```

### ADDSDomainControllerUninstallForceRemoval
```
Test-ADDSDomainControllerUninstallation [-LocalAdministratorPassword <SecureString>]
 [-Credential <PSCredential>] [-DemoteOperationMasterRole] [-ForceRemoval] [-NoRebootOnCompletion] [-Force]
 [<CommonParameters>]
```

## DESCRIPTION
The Test-ADDSDomainControllerUninstallation cmdlet runs those prerequisite checks (only) which would be performed if you were to use the Uninstall-ADDSDomainController cmdlet to uninstall a domain controller in Active Directory.
It differs from using the **-WhatIf** parameter with the Uninstall-ADDSDomainController cmdlet in that instead of summarizing the changes that would occur during the uninstallation process, this cmdlet actually tests whether those changes are possible given the current environment.

For more information on the scope of these prerequisite checks that the ADDSDeployment module performs when using this cmdlet see the section "Prerequisite Checking" in Understand and Troubleshoot AD DS Simplified Administrationhttp://go.microsoft.com/fwlink/?LinkID=237244.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
PS C:\> Test-ADDSDomainControllerUninstallation
```

Description

-----------

Runs the prerequisites (only) to determine if uninstalling an additional domain controller in a domain is possible and in such a way that it will prompt the user to set and confirm the local Administrator password prior to completing the uninstallation process.

## PARAMETERS

### -Credential
Specifies the user name and password that corresponds to the account used to install the domain controller.
To prompt the user to supply a password, use Runs the prerequisites (only) to determine if installing a domain controller is possible that includes a DNS server for the corp.contoso.com domain (using domain administrator credentials) and that prompts the user to correctly specify the Directory Services Restore Mode (DSRM) password."`(Get-Credential)`" in place of an existing *PSCredential* type.
This causes Windows PowerShell to prompt the user to enter credentials using the Windows security login UI.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: NULL
Accept pipeline input: False
Accept wildcard characters: False
```

### -DemoteOperationMasterRole
Indicates that (forced) demotion should continue even if an operations master role is discovered on domain controller from which AD DS is being removed.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: NULL
Accept pipeline input: False
Accept wildcard characters: False
```

### -DnsDelegationRemovalCredential
Specifies the account credentials (user name and password) to use when you create or remove the DNS delegation.
If you do not specify a value, the account credentials that you specify for the AD DS installation or removal are used to remove the DNS delegation.
As an alternative, you can specify the asterisk (*) to prompt the user to enter credentials.

```yaml
Type: PSCredential
Parameter Sets: ADDSDomainControllerUninstall
Aliases: 

Required: False
Position: Named
Default value: NULL
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
When this parameter is specified any warnings that might normally appear during the uninstallation and removal of the domain controller will be suppressed to allow the cmdlet to complete its operation.
This parameter can be useful to include when scripting uninstallation.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ForceRemoval
Forces the removal of a domain controller.
Use this parameter to force the uninstall of AD DS if you need to remove the domain controller and do not have connectivity to other domain controllers within the domain topology.

```yaml
Type: SwitchParameter
Parameter Sets: ADDSDomainControllerUninstallForceRemoval
Aliases: 

Required: True
Position: Named
Default value: NULL
Accept pipeline input: False
Accept wildcard characters: False
```

### -IgnoreLastDCInDomainMismatch
Used in conjunction with **-LastDomainControllerInDomain**.
This parameter specifies whether the Windows PowerShell ignores any inconsistency that it detects with the value that you specify for **-LastDomainControllerInDomain**.
For example, if you specify **-LastDomainControllerInDomain** but Windows PowerShell detects that there is actually another active domain controller in the domain, you can specify **-IgnoreLastDCInDomainMismatch** to have Windows PowerShell continue the removal of AD DS from the domain controller despite the inconsistency that it has detected.
Similarly, if you do not specify **-LastDomainControllerInDomain** but Windows PowerShell cannot detect that another domain controller is in the domain, you can specify **-IgnoreLastDCInDomainMismatch** to have Windows PowerShell continue to remove AD DS from the domain controller.

```yaml
Type: SwitchParameter
Parameter Sets: ADDSDomainControllerUninstall
Aliases: 

Required: False
Position: Named
Default value: NULL
Accept pipeline input: False
Accept wildcard characters: False
```

### -IgnoreLastDnsServerForZone
Specifies whether to continue the removal of AD DS despite the fact that the domain controller is the last DNS server for one or more of the Active Directory-integrated DNS zones that it hosts.

```yaml
Type: SwitchParameter
Parameter Sets: ADDSDomainControllerUninstall
Aliases: 

Required: False
Position: Named
Default value: NULL
Accept pipeline input: False
Accept wildcard characters: False
```

### -LastDomainControllerInDomain
Specifies whether the computer from which AD DS is being removed is the last domain controller in the domain.

```yaml
Type: SwitchParameter
Parameter Sets: ADDSDomainControllerUninstall
Aliases: 

Required: False
Position: Named
Default value: NULL
Accept pipeline input: False
Accept wildcard characters: False
```

### -LocalAdministratorPassword
Specifies a local administrator account password when AD DS is removed from a domain controller.
In earlier releases, where uninstall of AD DS was done using Dcpromo.exe for demotion, the default was to allow an empty password for this setting.
In Windows PowerShell, the ADDS Deployment module requires that a non-empty password string value be assigned.
If a value is not provided for this parameter, you will be prompted to enter a value for the password at the Windows PowerShell prompt.
The password value must be a secure string.

If this parameter is not specified, the cmdlet prompts you to enter and confirm a masked password.
This is the preferred usage when running the cmdlet interactively.
If additionally there are no other arguments specified with the cmdlet, you will be prompted to enter a masked password for this parameter but no confirmation of the password entered will be made (which is not recommended as it could allow a mistyped password to be configured).
Another available advanced option is to use the **ConvertTo-SecureString** cmdlet and specify the password string inline as unmasked console input, which is also not a recommended security best practice in production deployments.

```yaml
Type: SecureString
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: NULL
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoRebootOnCompletion
Specifies whether to not restart the computer upon completion, regardless of success.
(By default, reboot upon completion occurs when this cmdlet is used and this parameter is omitted.)

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemoveApplicationPartitions
Specifies whether to remove application partitions during the removal of AD DS from a domain controller.

```yaml
Type: SwitchParameter
Parameter Sets: ADDSDomainControllerUninstall
Aliases: 

Required: False
Position: Named
Default value: NULL
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemoveDnsDelegation
Specifies whether to preserve DNS delegations that point to this DNS server from the parent DNS zone.

By default, this parameter is set to FALSE, which means DNS delegations that point to this server from the parent DNS zone will not be retained after uninstallation of the domain controller.
This setting corresponds to the earlier Dcpromo.exe parameter default of /RemoveDNSDelegation:Yes.

```yaml
Type: SwitchParameter
Parameter Sets: ADDSDomainControllerUninstall
Aliases: 

Required: False
Position: Named
Default value: NULL
Accept pipeline input: False
Accept wildcard characters: False
```

### -RetainDCMetadata
If this parameter is used it indicates that the domain controller should retain metadata for the domain after removal of AD DS from it.

```yaml
Type: SwitchParameter
Parameter Sets: ADDSDomainControllerUninstall
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Uninstall-ADDSDomainController](./Uninstall-ADDSDomainController.md)

