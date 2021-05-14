---
external help file: Microsoft.DirectoryServices.Deployment.dll-Help.xml
Module Name: ADDSDeployment
online version: https://docs.microsoft.com/powershell/module/addsdeployment/add-addsreadonlydomaincontrolleraccount?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Add-ADDSReadOnlyDomainControllerAccount

## SYNOPSIS
Creates a read-only domain controller (RODC) account that can be used to install an RODC in Active Directory.

## SYNTAX

```
Add-ADDSReadOnlyDomainControllerAccount [-SkipPreChecks] -DomainControllerAccountName <String>
 -DomainName <String> -SiteName <String> [-AllowPasswordReplicationAccountName <String[]>]
 [-Credential <PSCredential>] [-DelegatedAdministratorAccountName <String>]
 [-DenyPasswordReplicationAccountName <String[]>] [-NoGlobalCatalog] [-InstallDns]
 [-ReplicationSourceDC <String>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The Add-ADDSReadOnlyDomainControllerAccount cmdlet creates a read-only domain controller (RODC) account that can be used to install an RODC in Active Directory.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
C:\PS>Add-ADDSReadOnlyDomainControllerAccount -DomainControllerAccountName RODC1 -DomainName corp.contoso.com -SiteName NorthAmerica
```

Description

-----------

Adds a new read-only domain controller (RODC) account to the corp.contoso.com domain using the North America site as the source site for the replication source domain controller.

## PARAMETERS

### -AllowPasswordReplicationAccountName
Specifies the names of user accounts, group accounts, and computer accounts whose passwords can be replicated to this RODC.
Use "None" if you want to keep the value empty.
By default, only the Allowed RODC Password Replication Group is allowed, and it is originally created empty.

```yaml
Type: String[]
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
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
Specifies the user name and password that corresponds to the account used to install the domain controller.
Specify "(get-credential)" when using this parameter to prompt the user to supply a password.

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

### -DelegatedAdministratorAccountName
Specifies the name of the user or group that will install and administer the RODC.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: NULL
Accept pipeline input: False
Accept wildcard characters: False
```

### -DenyPasswordReplicationAccountName
Specifies the names of user accounts, group accounts, and computer accounts whose passwords are not to be replicated to this RODC.
Use "None" if you do not want to deny the replication of credentials of any users or computers.
By default, Administrators, Server Operators, Backup Operators, Account Operators, and the Denied RODC Password Replication Group are denied.
By default, the Denied RODC Password Replication Group includes Cert Publishers, Domain Admins, Enterprise Admins, Enterprise Domain Controllers, Enterprise Read-Only Domain Controllers, Group Policy Creator Owners, the krbtgt account, and Schema Admins.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: NULL
Accept pipeline input: False
Accept wildcard characters: False
```

### -DomainControllerAccountName
Specifies the name of the RODC account that you are creating.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: <mandatory>
Accept pipeline input: False
Accept wildcard characters: False
```

### -DomainName
Specifies the domain name for the user name (account credentials) for the operation.
This parameter is required.
It also helps to specify the forest where you plan to install the domain controller or create an RODC account.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: <mandatory>
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Forces completion of the cmdlet even if issues are found in the process of creating the RODC account.

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

### -InstallDns
Specifies whether the DNS Server service should be installed.
If no value is provided, the default behavior is to automatically compute DNS configuration behavior based upon the existing environment.

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

### -NoGlobalCatalog
Specifies that the read-only domain controller (RODC) will not be a global catalog server.

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

### -ReplicationSourceDC
Specifies the name of the domain controller to be used as the source for replicating to this RODC.

```yaml
Type: String
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
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: <mandatory>
Accept pipeline input: False
Accept wildcard characters: False
```

### -SkipPreChecks
Specifies that only a base set of validations will be performed when this cmdlet is executed.
This behavior is equivalent to the validations that were performed when using Dcpromo.exe in earlier versions of Windows Server to add a domain controller.
When this switch parameter is set, it specifies that additional preliminary checks should be bypassed.
For more information on the scope of these additional preliminary checks that the ADDSDeployment module performs by default when using Windows Server 2012, refer to the table in the section "Prerequisite Checking" in the Understand and Troubleshoot AD DS Simplified Administration in Windows Server 2012 guide located at http://go.microsoft.com/fwlink/?LinkID=237244.

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

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES
* Once you have added the RODC account, you can add an RODC to a server computer by using the **Install-ADDSDomainController** cmdlet with the **-ReadOnlyReplica** switch parameter.
* You can also delegate the ability to attach the server to a non-administrative group or user. If you are deploying RODCs in delegated administration scenarios where the machine accounts are pre-provisioned, creating the RODC account is the first stage of the RODC installation process and needs to be done by a member of the Domain Admins group. In these scenarios, once an administrator uses this cmdlet to add the RODC account in Active Directory Domain Services (AD DS), the second stage of the installation can occur. This involves attaching an actual server computer in a remote location (such as a branch office) that will operate as the RODC for the specified account created using this cmdlet.

## RELATED LINKS

[Install-ADDSDomainController](./Install-ADDSDomainController.md)

