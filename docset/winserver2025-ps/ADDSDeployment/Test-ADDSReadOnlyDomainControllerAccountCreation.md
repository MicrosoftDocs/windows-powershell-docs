---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.DirectoryServices.Deployment.dll-Help.xml
Module Name: ADDSDeployment
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/addsdeployment/test-addsreadonlydomaincontrolleraccountcreation?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Test-ADDSReadOnlyDomainControllerAccountCreation
---

# Test-ADDSReadOnlyDomainControllerAccountCreation

## SYNOPSIS
Runs the prerequisites for adding a RODC account.

## SYNTAX

```
Test-ADDSReadOnlyDomainControllerAccountCreation -DomainControllerAccountName <String>
 -DomainName <String> -SiteName <String> [-AllowPasswordReplicationAccountName <String[]>]
 [-Credential <PSCredential>] [-DelegatedAdministratorAccountName <String>]
 [-DenyPasswordReplicationAccountName <String[]>] [-NoGlobalCatalog] [-InstallDns]
 [-ReplicationSourceDC <String>] [-Force] [<CommonParameters>]
```

## DESCRIPTION

The `Test-ADDSReadOnlyDomainControllerAccountCreation` cmdlet runs the prerequisite checks which
would be performed if you were to add a read-only domain controller (RODC) account in Active
Directory using the `Add-ADDSReadOnlyDomainControllerAccount` cmdlet. It differs from using the
**WhatIf** parameter with the `Add-ADDSReadOnlyDomainControllerAccount` cmdlet in that instead of
summarizing the changes that would occur during the account creation process, this cmdlet actually
tests whether those changes are possible given the current environment.

## EXAMPLES

### Example 1: Test adding an RODC account to confirm it is possible

```powershell
$HashArguments = @{
    DomainControllerAccountName = RODC1
    DomainName                  = "corp.contoso.com"
    SiteName                    = "NorthAmerica"
}
Test-ADDSReadOnlyDomainControllerAccountCreation @HashArguments
```

This command runs the prerequisites for adding an RODC account to the `corp.contoso.com` domain that
would use the North America site as the source site for the replication source domain controller.

## PARAMETERS

### -AllowPasswordReplicationAccountName

Specifies the names of user accounts, group accounts, and computer accounts whose passwords can be
replicated to this RODC. Use `None` if you want to keep the value empty. By default, only the
Allowed RODC Password Replication Group is allowed, and it is originally created empty.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: NULL
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential

Specifies the user name and password that corresponds to the account used to install the domain
controller. Use the `Get-Credential` cmdlet to prompt the user to supply a password.

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

### -DelegatedAdministratorAccountName

Specifies the name of the user or group that installs and administer the RODC.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: NULL
Accept pipeline input: False
Accept wildcard characters: False
```

### -DenyPasswordReplicationAccountName

Specifies the names of user accounts, group accounts, and computer accounts whose passwords are not
to be replicated to this RODC. Use `None` if you do not want to deny the replication of credentials
of any users or computers. By default, Administrators, Server Operators, Backup Operators, Account
Operators, and the Denied RODC Password Replication Group are denied. By default, the Denied RODC
Password Replication Group includes Cert Publishers, Domain Admins, Enterprise Admins, Enterprise
Domain Controllers, Enterprise Read-Only Domain Controllers, Group Policy Creator Owners, the
krbtgt account, and Schema Admins.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: NULL
Accept pipeline input: False
Accept wildcard characters: False
```

### -DomainControllerAccountName

Specifies the name of the RODC account that this cmdlet creates.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: <mandatory>
Accept pipeline input: False
Accept wildcard characters: False
```

### -DomainName

Specifies the domain name for the user name for the operation. This parameter is required. You
should specify the forest where you plan to install the domain controller or create an RODC account.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: <mandatory>
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

### -InstallDns

Indicates that the cmdlet installs the DNS Server service. The default is automatically computed
based on the environment.

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

### -NoGlobalCatalog

Indicates that the RODC is not a global catalog server.

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

### -ReplicationSourceDC

Specifies the name of the fully writable domain controller to use in the creation of the RODC
account in Active Directory.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: NULL
Accept pipeline input: False
Accept wildcard characters: False
```

### -SiteName

Specifies the name of an existing site where you can place the new domain controller. The default
value depends on the type of installation. For a new forest, the default is
`Default-First-Site-Name`. For all other installations, the default is the site that is associated
with the subnet that includes the IP address of this server. If no such site exists, the default is
the site of the replication source domain controller.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: <mandatory>
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

[Add-ADDSReadOnlyDomainControllerAccount](./Add-ADDSReadOnlyDomainControllerAccount.md)

[Get-Credential](https://go.microsoft.com/fwlink/?LinkID=293936)
