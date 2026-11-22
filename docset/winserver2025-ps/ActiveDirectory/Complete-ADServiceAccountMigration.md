---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
Module Name: ActiveDirectory
ms.date: 02/15/2024
online version: https://learn.microsoft.com/powershell/module/activedirectory/complete-adserviceaccountMigration?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Complete-ADServiceAccountMigration
---


# Complete-ADServiceAccountMigration

## SYNOPSIS
Completes the migration process and supersedes a normal user account to a delegated managed service
account.

## SYNTAX

### ADServiceAccountMigrationParameterSet (Default)

```
Complete-ADServiceAccountMigration [-AuthType <ADAuthType>] [-Credential <PSCredential>]
 [-Identity] <ADServiceAccount> [-SupersededAccount <String>] [-Server <String>]
 [<CommonParameters>]
```

## DESCRIPTION

The `Complete-ADServiceAccountMigration` cmdlet will complete the migration process of superseding
a normal user account specificed by the distinguished name string provided in the
**SupersededAccount** parameter to the delegated managed service account provided in the
**identity** parameter. They must've been previously linked via the
`Start-ADServiceAccountMigration` cmdlet.

The **Identity** parameter specifies the delegated managed service account to use. You can identify
a managed service account by its distinguished name, GUID, security identifier (SID), or Security
Account Manager (SAM) account name.

The **SupersededAccount** parameter specifies the user account that's linked to the delegated
managed service account. The superseded account must be identified by its distinguished name.

## EXAMPLES

### Example 1: Complete a service account migration using the Security Account Manager name of the delegated managed service account

```powershell
$params = @{
    Identity = "delegatedSvc1"
    SupersededAccount = "CN=User1,OU=Accounts,DC=Contoso,DC=com"
}
Complete-ADServiceAccountMigration @params
```

### Example 2: Complete a service account migration by specifying a 2025 Domain Controller

```powershell
$params = @{
    Identity = "delegatedSvc1"
    SupersededAccount = "CN=User1,OU=Accounts,DC=Contoso,DC=com"
    Server = "2025DC.Contoso.com"
}
Complete-ADServiceAccountMigration @params
```

## PARAMETERS

### -AuthType

Specifies the authentication method to use.
The acceptable values for this parameter are:

- Negotiate or 0
- Basic or 1

The default authentication method is Negotiate.

A Secure Sockets Layer (SSL) connection is required for the Basic authentication method.

```yaml
Type: ADAuthType
Parameter Sets: (All)
Aliases:
Accepted values: Negotiate, Basic

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential

Specifies the user account credentials to use to perform this task. The default credentials are the
credentials of the currently logged on user unless the cmdlet is run from an Active Directory
module for Windows PowerShell provider drive. If the cmdlet is run from such a provider drive, the
account associated with the drive is the default.

To specify this parameter, you can type a user name, such as `User1` or `Domain01\User01` or you
can specify a **PSCredential** object. If you specify a user name for this parameter, the cmdlet
prompts for a password.

You can also create a **PSCredential** object by using a script or by using the `Get-Credential`
cmdlet. You can then set the *Credential* parameter to the **PSCredential** object.

If the acting credentials don't have directory-level permission to perform the task, Active
Directory module for Windows PowerShell returns a terminating error.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Identity

Specifies an Active Directory account object by providing one of the following property values. The
identifier in parentheses is the LDAP display name for the attribute. The acceptable values for
this parameter are:

- A distinguished name
- A GUID (objectGUID)
- A security identifier (objectSid)
- A SAM account name (sAMAccountName)

The cmdlet searches the default naming context or partition to find the object.
If two or more objects are found, the cmdlet returns a non-terminating error.

```yaml
Type: ADServiceAccount
Parameter Sets: ADServiceAccountMigrationParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SupersededAccount

Specifies the user account that you want to be migrated to a delegated managed service account. The
account must be specified by it's distinguished name.

```yaml
Type: String
Parameter Sets: ADServiceAccountMigrationParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Server

Specifies the Active Directory Domain Services instance to connect to, by providing one of the
following values for a corresponding domain name or directory server. The service may be any of the
following: Active Directory Lightweight Domain Services, Active Directory Domain Services or Active
Directory Snapshot instance.

Domain name values:

- Fully qualified domain name (FQDN)
- NetBIOS name

Directory server values:

- Fully qualified directory server name
- NetBIOS name
- Fully qualified directory server name and port

The default value for the **Server** parameter is determined by one of the following methods in the
order that they are listed:

- By using **Server** value from objects passed through the pipeline.
- By using the server information associated with the Active Directory PowerShell provider drive,
  when running under that drive.
- By using the domain of the computer running PowerShell.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`,
`-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`,
`-Verbose`, `-WarningAction`, and `-WarningVariable`. For more information, see
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.ActiveDirectory.Management.ADServiceAccount

A delegated managed service account object is received by the **Identity** parameter.

## NOTES

- This cmdlet doesn't work with AD LDS.
- This cmdlet doesn't work with an Active Directory snapshot.
- This cmdlet doesn't work with a read-only domain controller.
- This cmdlet requires that you create a Microsoft Group Key Distribution Service (GKDS) root key
  first to begin using group managed service accounts in your Active Directory deployment. For more
  information on how to create the GKDS root key using Windows PowerShell, see
  [Create the Key Distribution Services KDS Root Key](https://go.microsoft.com/fwlink/?LinkId=253584).

## RELATED LINKS

[Reset-ADServiceAccountMigration](./Reset-ADServiceAccountMigration.md)

[Start-ADServiceAccountMigration](./Start-ADServiceAccountMigration.md)

[Undo-ADServiceAccountMigration](./Undo-ADServiceAccountMigration.md)

[Get-ADServiceAccount](./Get-ADServiceAccount.md)

[New-ADServiceAccount](./New-ADServiceAccount.md)

[Set-ADServiceAccount](Set-ADServiceAccount.md)
