---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.DirectoryServices.Deployment.dll-Help.xml
Module Name: ADDSDeployment
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/addsdeployment/test-addsdomaincontrolleruninstallation?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Test-ADDSDomainControllerUninstallation
---

# Test-ADDSDomainControllerUninstallation

## SYNOPSIS
Runs the prerequisites for uninstalling a domain controller in Active Directory.

## SYNTAX

### ADDSDomainControllerUninstall (Default)

```
Test-ADDSDomainControllerUninstallation [-LocalAdministratorPassword <SecureString>]
 [-Credential <PSCredential>] [-DemoteOperationMasterRole]
 [-DnsDelegationRemovalCredential <PSCredential>] [-IgnoreLastDCInDomainMismatch]
 [-IgnoreLastDnsServerForZone] [-LastDomainControllerInDomain] [-NoRebootOnCompletion]
 [-RemoveApplicationPartitions] [-RemoveDnsDelegation] [-RetainDCMetadata] [-Force]
 [<CommonParameters>]
```

### ADDSDomainControllerUninstallForceRemoval

```
Test-ADDSDomainControllerUninstallation [-LocalAdministratorPassword <SecureString>]
 [-Credential <PSCredential>] [-DemoteOperationMasterRole] [-ForceRemoval]
 [-NoRebootOnCompletion] [-Force] [<CommonParameters>]
```

## DESCRIPTION

The `Test-ADDSDomainControllerUninstallation` cmdlet runs those prerequisite checks which would be
performed if you were to use the `Uninstall-ADDSDomainController` cmdlet to uninstall a domain
controller in Active Directory. It differs from using the **WhatIf** parameter with the
`Uninstall-ADDSDomainController` cmdlet in that instead of summarizing the changes that would occur
during the uninstallation process, this cmdlet actually tests whether those changes are possible
given the current environment.

For more information on the scope of these prerequisite checks that the **ADDSDeployment** module
performs when using this cmdlet see the section ADPrep and Prerequisite Checking Architecture in
[AD DS Simplified Administration](https://go.microsoft.com/fwlink/?LinkID=237244).

## EXAMPLES

### Example 1: Test if uninstalling a domain controller is possible

```powershell
Test-ADDSDomainControllerUninstallation
```

This command runs the prerequisites to determine if the uninstall of an additional domain controller
in a domain is possible. The command also prompts the user to set and confirm the local
Administrator password prior to completing the uninstallation process.

## PARAMETERS

### -Credential

Specifies the user name and password that corresponds to the account used to install the domain
controller. To prompt the user to supply a password, use Runs the prerequisites (only) to determine
if installing a domain controller is possible that includes a DNS server for the `corp.contoso.com`
domain, using domain administrator credentials, and then prompts the user to correctly specify the
Directory Services Restore Mode (DSRM) password. Use the `Get-Credential` cmdlet in place of an
existing **PSCredential** type. This parameter will cause Windows PowerShell to prompt the user to
enter credentials using the Windows security login UI.

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: NULL
Accept pipeline input: False
Accept wildcard characters: False
```

### -DemoteOperationMasterRole

Indicates that forced demotion should continue even if an operations master role is discovered on
the domain controller from which AD DS is being removed.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: NULL
Accept pipeline input: False
Accept wildcard characters: False
```

### -DnsDelegationRemovalCredential

Specifies the account credentials to use when you create or remove the DNS delegation. If you do
not specify a value, the account credentials that you specify for the AD DS installation or removal
are used to remove the DNS delegation. As an alternative, you can specify the asterisk (`*`) to
prompt the user to enter credentials.

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: ADDSDomainControllerUninstall
Aliases: 

Required: False
Position: Named
Default value: NULL
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

Forces the command to run without asking for user confirmation.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ForceRemoval

Indicates that the cmdlet forces the removal of a domain controller. Use this parameter to force the
uninstall of AD DS if you need to remove the domain controller and do not have connectivity to other
domain controllers within the domain topology.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ADDSDomainControllerUninstallForceRemoval
Aliases: 

Required: True
Position: Named
Default value: NULL
Accept pipeline input: False
Accept wildcard characters: False
```

### -IgnoreLastDCInDomainMismatch

Indicates that Windows PowerShell ignores any inconsistency that it detects with the value that you
specify for the **LastDomainControllerInDomain** parameter. For instance, if you specify
**LastDomainControllerInDomain** but Windows PowerShell detects that there is actually another
active domain controller in the domain, you can specify the **IgnoreLastDCInDomainMismatch**
parameter to have Windows PowerShell continue the removal of AD DS from the domain controller
despite the inconsistency that it has detected. Similarly, if you do not specify
**LastDomainControllerInDomain** but Windows PowerShell is unable to detect that another domain
controller is in the domain, you can specify **IgnoreLastDCInDomainMismatch** to have Windows
PowerShell continue to remove AD DS from the domain controller.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ADDSDomainControllerUninstall
Aliases: 

Required: False
Position: Named
Default value: NULL
Accept pipeline input: False
Accept wildcard characters: False
```

### -IgnoreLastDnsServerForZone

Indicates that the cmdlet continues the removal of AD DS despite the fact that the domain controller
is the last DNS server for one or more of the Active Directory-integrated DNS zones that it hosts.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ADDSDomainControllerUninstall
Aliases: 

Required: False
Position: Named
Default value: NULL
Accept pipeline input: False
Accept wildcard characters: False
```

### -LastDomainControllerInDomain

Indicates that the cmdlet removes AD DS from the last controller in the domain.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ADDSDomainControllerUninstall
Aliases: 

Required: False
Position: Named
Default value: NULL
Accept pipeline input: False
Accept wildcard characters: False
```

### -LocalAdministratorPassword

Specifies a local administrator account password when AD DS is removed from a domain controller. In
earlier releases, where uninstall of AD DS was done using `Dcpromo.exe` for demotion, the default
was to allow an empty password for this setting. In Windows PowerShell, the ADDS Deployment module
requires that a non-empty password string value be assigned. If a value is not provided for this
parameter, you are prompted to enter a value for the password at the Windows PowerShell prompt. The
password value must be a secure string.

If this parameter is not specified, the cmdlet prompts you to enter and confirm a masked password.
This is the preferred usage when running the cmdlet interactively. If additionally there are no
other arguments specified with the cmdlet, you are prompted to enter a masked password for this
parameter but no confirmation of the password entered is made. This is not recommended as it could
allow a mistyped password to be configured. Another available advanced option is to use the
`ConvertTo-SecureString` cmdlet and specify the password string inline as unmasked console input,
which is also not a recommended security best practice in production deployments.

```yaml
Type: System.Security.SecureString
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: NULL
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoRebootOnCompletion

Indicates that the cmdlet does not restart the computer upon completion, regardless of success. By
default, reboot upon completion occurs when this cmdlet is used and this parameter is omitted.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemoveApplicationPartitions

Indicates that the cmdlet removes application partitions during the removal of AD DS from a domain
controller.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ADDSDomainControllerUninstall
Aliases: 

Required: False
Position: Named
Default value: NULL
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemoveDnsDelegation

Indicates that the cmdlet preserves DNS delegations that point to this DNS server from the parent
DNS zone.

By default, this parameter is set to `$false`, which means DNS delegations that point to this
server from the parent DNS zone will not be retained after uninstallation of the domain controller.
This setting corresponds to the earlier `Dcpromo.exe` parameter default of
`/RemoveDNSDelegation:Yes`.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ADDSDomainControllerUninstall
Aliases: 

Required: False
Position: Named
Default value: NULL
Accept pipeline input: False
Accept wildcard characters: False
```

### -RetainDCMetadata

Indicates that the domain controller should retain metadata for the domain after removal of AD DS.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ADDSDomainControllerUninstall
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[AD DS Simplified Administration](https://go.microsoft.com/fwlink/?LinkID=237244)

[Uninstall-ADDSDomainController](./Uninstall-ADDSDomainController.md)

[Get-Credential](https://go.microsoft.com/fwlink/?LinkID=293936)

[ConvertTo-SecureString](https://go.microsoft.com/fwlink/p/?LinkId=113291)
