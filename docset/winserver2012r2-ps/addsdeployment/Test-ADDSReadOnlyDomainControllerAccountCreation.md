---
external help file: Microsoft.DirectoryServices.Deployment.dll-Help.xml
Module Name: ADDSDeployment
ms.date: 10/30/2017
online version: https://docs.microsoft.com/powershell/module/addsdeployment/test-addsreadonlydomaincontrolleraccountcreation?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Test-ADDSReadOnlyDomainControllerAccountCreation
---

# Test-ADDSReadOnlyDomainControllerAccountCreation

## SYNOPSIS
Runs the prerequisites (only) for adding a read-only domain controller (RODC) account.

## SYNTAX

```
Test-ADDSReadOnlyDomainControllerAccountCreation -DomainControllerAccountName <String> -DomainName <String>
 -SiteName <String> [-AllowPasswordReplicationAccountName <String[]>] [-Credential <PSCredential>]
 [-DelegatedAdministratorAccountName <String>] [-DenyPasswordReplicationAccountName <String[]>]
 [-NoGlobalCatalog] [-InstallDns] [-ReplicationSourceDC <String>] [-Force] [<CommonParameters>]
```

## DESCRIPTION
The Test-ADDSReadOnlyDomainControllerAccountCreation cmdlet runs the prerequisite checks (only) which would be performed if you were to add a read-only domain controller (RODC) account in Active Directory using the Add-ADDSReadOnlyDomainControllerAccount cmdlet.
It differs from using the **-WhatIf** parameter with the Add-ADDSReadOnlyDomainControllerAccount cmdlet in that instead of summarizing the changes that would occur during the account creation process, this cmdlet actually tests whether those changes are possible given the current environment.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
PS C:\> Test-ADDSReadOnlyDomainControllerAccountCreation -DomainControllerAccountName RODC1 -DomainName corp.contoso.com -SiteName NorthAmerica
```

Description

-----------

Runs the prerequisites (only) for adding an RODC account to the corp.contoso.com domain that would use the North America site as the source site for the replication source domain controller.

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

### -Credential
Specifies the user name and password that corresponds to the account used to install the domain controller.
Specify "`(Get-Credential)`" when using this parameter to prompt the user to supply a password.

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
The default is automatically computed based on the environment.

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
Specifies the name of the fully writable domain controller to use in creating the RODC account in Active Directory.

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
The default value depends on the type of installation.
For a new forest, the default is Default-First-Site-Name.
For all other installations, the default is the site that is associated with the subnet that includes the IP address of this server.
If no such site exists, the default is the site of the replication source domain controller.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-ADDSReadOnlyDomainControllerAccount](./Add-ADDSReadOnlyDomainControllerAccount.md)

