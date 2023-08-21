---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.DirectoryServices.Deployment.dll-Help.xml
Module Name: ADDSDeployment
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/addsdeployment/add-addsreadonlydomaincontrolleraccount?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-ADDSReadOnlyDomainControllerAccount
---

# Add-ADDSReadOnlyDomainControllerAccount

## SYNOPSIS
Creates a RODC account that can be used to install an RODC in Active Directory.

## SYNTAX

```
Add-ADDSReadOnlyDomainControllerAccount [-SkipPreChecks]
 -DomainControllerAccountName <String> -DomainName <String>
 -SiteName <String> [-AllowPasswordReplicationAccountName <String[]>]
 [-Credential <PSCredential>] [-DelegatedAdministratorAccountName <String>]
 [-DenyPasswordReplicationAccountName <String[]>] [-NoGlobalCatalog] [-InstallDns]
 [-ReplicationSourceDC <String>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

The `Add-ADDSReadOnlyDomainControllerAccount` cmdlet creates a read-only domain controller (RODC)
account that can be used to install an RODC in Active Directory.

## EXAMPLES

### Example 1: Add a RODC account

```powershell
$HashArguments = @{
    DomainControllerAccountName = "RODC1"
    DomainName                  = "corp.contoso.com"
    SiteName                    = "NorthAmerica"
}
Add-ADDSReadOnlyDomainControllerAccount @HashArguments
```

This command adds a RODC account to the `corp.contoso.com` domain using the North America site as the
source site for the replication source domain controller.

## PARAMETERS

### -AllowPasswordReplicationAccountName

Specifies an array of user accounts, group accounts, and computer accounts whose passwords can be
replicated to this RODC. Use None if you want to keep the value empty. By default, only the Allowed
RODC Password Replication Group is allowed, and it is originally created empty.

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

### -Confirm

Prompts you for confirmation before running the cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential

Specifies the user name and password that corresponds to the account used to install the domain
controller. Specify the `Get-Credential` cmdlet when using this parameter to prompt the user to
supply a password.

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

Specifies the name of the user or group that installs and administers the RODC.

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
to be replicated to this RODC. Use None if you do not want to deny the replication of credentials of
any users or computers. By default, Administrators, Server Operators, Backup Operators, Account
Operators, and the Denied RODC Password Replication Group are denied. By default, the Denied RODC
Password Replication Group includes Cert Publishers, Domain Admins, Enterprise Admins, Enterprise
Domain Controllers, Enterprise Read-Only Domain Controllers, Group Policy Creator Owners, the krbtgt
account, and Schema Admins.

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

Specifies the domain name for the user name for the operation. This parameter is required. It also
helps to specify the forest where you plan to install the domain controller or create an RODC
account.

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

Indicates that the cmdlet installs the DNS Server service. If no value is provided, the default
behavior is to automatically compute DNS configuration behavior based upon the existing environment.

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

Indicates that the cmdlet does not set the RODC as a global catalog server.

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

Specifies the name of the domain controller to be used as the source for replicating to this RODC.

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

Specifies the name of an existing site where you can place the new domain controller.

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

### -SkipPreChecks

Indicates that the cmdlet executes only a base set of validations. This behavior is equivalent to
the validations that were performed when using `Dcpromo.exe` in earlier versions of Windows Server
to add a domain controller. When this switch parameter is set, it specifies that additional
preliminary checks should be bypassed. For more information on the scope of these additional
preliminary checks that the **ADDSDeployment** module performs by default when using Windows Server
2012, refer to the table in the section ADPrep and Prerequisite Checking Architecture in
[AD DS Simplified Administration](https://go.microsoft.com/fwlink/?LinkID=237244).

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

### -WhatIf

Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
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

- Once you have added the RODC account, you can add an RODC to a server computer by using the
  `Install-ADDSDomainController` cmdlet with the `-ReadOnlyReplica` switch parameter.
- You can also delegate the ability to attach the server to a non-administrative group or user. If
  you are deploying RODCs in delegated administration scenarios where the machine accounts are
  pre-provisioned, creating the RODC account is the first stage of the RODC installation process and
  needs to be done by a member of the Domain Admins group. In these scenarios, once an administrator
  uses this cmdlet to add the RODC account in Active Directory Domain Services (AD DS), the second
  stage of the installation can occur. This involves attaching an actual server computer in a remote
  location (such as a branch office) that will operate as the RODC for the specified account created
  using this cmdlet.

## RELATED LINKS

[AD DS Simplified Administration](https://go.microsoft.com/fwlink/?LinkID=237244)

[Install-ADDSDomainController](./Install-ADDSDomainController.md)

[Get-Credential](https://go.microsoft.com/fwlink/?LinkID=293936)
