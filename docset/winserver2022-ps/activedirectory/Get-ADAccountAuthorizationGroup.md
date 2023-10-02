---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
Module Name: ActiveDirectory
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/activedirectory/get-adaccountauthorizationgroup?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ADAccountAuthorizationGroup
---

# Get-ADAccountAuthorizationGroup

## SYNOPSIS
Gets the accounts token group information.

## SYNTAX

```
Get-ADAccountAuthorizationGroup [-AuthType <ADAuthType>] [-Credential <PSCredential>]
 [-Identity] <ADAccount> [-Partition <String>] [-Server <String>] [<CommonParameters>]
```

## DESCRIPTION

The `Get-ADAccountAuthorizationGroup` cmdlet gets the security groups from the specified user,
computer, or service accounts token. This cmdlet requires a global catalog to perform the group
search. If the forest that contains the account doesn't have a global catalog, the cmdlet returns a
non-terminating error.

The **Identity** parameter specifies the user, computer, or service account. You can identify a
user, computer, or service account object by its distinguished name, GUID, security identifier
(SID), Security Account Manager (SAM) account name or user principal name. You can also set the
**Identity** parameter to an account object variable, such as `$<localAccountObject>`, or pass an
account object through the pipeline to the **Identity** parameter. For example, you can use the
`Get-ADUser`, `Get-ADComputer`, `Get-ADServiceAccount` or `Search-ADAccount` cmdlets to retrieve an
account object and then pass the object through the pipeline to the
`Get-ADAccountAuthorizationGroup` cmdlet.

## EXAMPLES

### Example 1: Get all security groups for a specified account

```powershell
Get-ADAccountAuthorizationGroup -Identity DavidCh
```

```output
GroupScope        : DomainLocal
objectGUID        : 00000000-0000-0000-0000-000000000000
GroupCategory     : Security
SamAccountName    : Everyone
name              : Everyone
objectClass       : SID               : S-1-1-0
distinguishedName : GroupScope        : DomainLocal
objectGUID        : 00000000-0000-0000-0000-000000000000
GroupCategory     : Security
SamAccountName    : Authenticated Users
name              : Authenticated Users
objectClass       : SID               : S-1-5-11
distinguishedName : GroupScope        : Global
objectGUID        : 86c0f0d5-8b4d-4f35-a867-85a006b92902
GroupCategory     : Security
SamAccountName    : Domain Users
name              : Domain Users
objectClass       : group
SID               : S-1-5-21-41432690-3719764436-1984117282-513
distinguishedName : CN=Domain Users,CN=Users,DC=Fabrikam,DC=com

GroupScope        : DomainLocal
objectGUID        : 869fb7ad-8cf2-4dd0-ac0f-4bd3bf324669
GroupCategory     : Security
SamAccountName    : Pre-Windows 2000 Compatible Access
name              : Pre-Windows 2000 Compatible Access
objectClass       : group
SID               : S-1-5-32-554
distinguishedName : CN=Pre-Windows 2000 Compatible Access,CN=Builtin,DC=Fabrikam,DC=com

GroupScope        : DomainLocal
objectGUID        : c1e397c5-1e44-4270-94d1-88d6c4b78ee6
GroupCategory     : Security
SamAccountName    : Users
name              : Users
objectClass       : group
SID               : S-1-5-32-545
distinguishedName : CN=Users,CN=Builtin,DC=Fabrikam,DC=com
```

This command returns all security groups for the specified account with **SamAccountName**
`DavidCh`.

### Example 2: Get all security groups for a specified account using a distinguished name

```powershell
Get-ADAccountAuthorizationGroup -Identity "CN=DavidCh,DC=AppNC" -Server "<Server>:50000"
```

```output
distinguishedName : CN=AdminGroup,DC=AppNC
GroupCategory     : Security
GroupScope        : Global
name              : AdminGroup
objectClass       : group
objectGUID        : 4d72873f-fe09-4834-9ada-a905636d10df
SamAccountName    : AdminGroup
SID               : S-1-510474493-936115905-4021890855-1253703389-3958791574-3542197427
```

This command returns all security groups for the specified account with **DistinguishedName**
`CN=DavidCh,DC=AppNC` in the AD LDS instance `<Server>:50000`.

### Example 3: Get a filtered list of security groups

```powershell
Get-ADAccountAuthorizationGroup -Server "<Server>:50000" -Identity Administrator |
    Where-Object { $_.objectClass -ne $null } |
    Select-Object name, objectClass
```

```output
name                                                        objectClass
----                                                        -----------
Domain Users                                                group
Administrators                                              group
Users                                                       group
Pre-Windows 2000 Compatible Access                          group
Group Policy Creator Owners                                 group
Domain Admins                                               group
Enterprise Admins                                           group
Schema Admins                                               group
Denied RODC Password Replication Group                      group
```

This command returns a filtered list of built-in security groups that do not have an empty or null
setting for **objectClass**, such as **Everyone** or **Authenticated Users**.

> [!NOTE]
> This type of filtering of groups in output can be useful when piping the output of this
> cmdlet to be used as input to other Active Directory cmdlets.

## PARAMETERS

### -AuthType

Specifies the authentication method to use.
The acceptable values for this parameter are:

- `Negotiate` or `0`
- `Basic` or `1`

The default authentication method is `Negotiate`.

A Secure Sockets Layer (SSL) connection is required for the `Basic` authentication method.

```yaml
Type: Microsoft.ActiveDirectory.Management.ADAuthType
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
credentials of the currently logged on user unless the cmdlet is run from an Active Directory module
for Windows PowerShell provider drive. If the cmdlet is run from such a provider drive, the account
associated with the drive is the default.

To specify this parameter, you can type a user name, such as `User1` or `Domain01\User01` or you can
specify a **PSCredential** object. If you specify a user name for this parameter, the cmdlet prompts
for a password.

You can also create a **PSCredential** object by using a script or by using the `Get-Credential`
cmdlet. You can then set the **Credential** parameter to the **PSCredential** object.

If the acting credentials do not have directory-level permission to perform the task, Active
Directory module for Windows PowerShell returns a terminating error.

```yaml
Type: System.Management.Automation.PSCredential
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
identifier in parentheses is the Lightweight Directory Access Protocol (LDAP) display name for the
attribute. The acceptable values for this parameter are:

- A distinguished name
- A GUID (**objectGUID**)
- A Security Identifier (**objectSid**)
- A SAM Account Name (**SAMAccountName**)

The cmdlet searches the default naming context or partition to find the object. If two or more
objects are found, the cmdlet returns a non-terminating error.

This parameter can also get this object through the pipeline or you can set this parameter to an
account object instance.

Derived types such as the following are also accepted:

- **Microsoft.ActiveDirectory.Management.ADServiceAccount**
- **Microsoft.ActiveDirectory.Management.ADComputer**
- **Microsoft.ActiveDirectory.Management.ADUser**

```yaml
Type: Microsoft.ActiveDirectory.Management.ADAccount
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Partition

Specifies the distinguished name of an Active Directory partition. The distinguished name must be
one of the naming contexts on the current directory server. The cmdlet searches this partition to
find the object defined by the **Identity** parameter.

In many cases, a default value is used for the **Partition** parameter if no value is specified. The
rules for determining the default value are given below. Note that rules listed first are evaluated
first and once a default value can be determined, no further rules are evaluated.

In Active Directory Domain Services environments, a default value for **Partition** is set in the
following cases:

- If the **Identity** parameter is set to a distinguished name, the default value of **Partition**
  is automatically generated from this distinguished name.
- If running cmdlets from an Active Directory provider drive, the default value of **Partition** is
  automatically generated from the current path in the drive.
- If none of the previous cases apply, the default value of **Partition** is set to the default
  partition or naming context of the target domain.

In Active Directory Lightweight Directory Services (AD LDS) environments, a default value for
**Partition** is set in the following cases:

- If the **Identity** parameter is set to a distinguished name, the default value of **Partition**
  is automatically generated from this distinguished name.
- If running cmdlets from an Active Directory provider drive, the default value of **Partition** is
  automatically generated from the current path in the drive.
- If the target AD LDS instance has a default naming context, the default value of **Partition** is
  set to the default naming context. To specify a default naming context for an AD LDS environment,
  set the **msDS-defaultNamingContext** property of the Active Directory directory service agent
  (DSA) object (**nTDSDSA**) for the AD LDS instance.
- If none of the previous cases apply, the **Partition** parameter will not take any default value.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Server

Specifies the Active Directory Domain Services instance to connect to, by providing one of the
following values for a corresponding domain name or directory server. The service may be any of the
following: Active Directory Lightweight Domain Services, Active Directory Domain Services or Active
Directory snapshot instance.

Specify the Active Directory Domain Services instance in one of the following ways:

Domain name values:

- Fully qualified domain name
- NetBIOS name

Directory server values:

- Fully qualified directory server name
- NetBIOS name
- Fully qualified directory server name and port

The default value for this parameter is determined by one of the following methods in the order that
they are listed:

- By using the **Server** value from objects passed through the pipeline
- By using the server information associated with the Active Directory Domain Services Windows
  PowerShell provider drive, when the cmdlet runs in that drive
- By using the domain of the computer running Windows PowerShell

```yaml
Type: System.String
Parameter Sets: (All)
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

### Microsoft.ActiveDirectory.Management.ADAccount

An account object that represents the user, computer or service account is received by the
**Identity** parameter. Derived types, such as the following are also accepted:

- **Microsoft.ActiveDirectory.Management.ADUser**
- **Microsoft.ActiveDirectory.Management.ADComputer**
- **Microsoft.ActiveDirectory.Management.ADServiceAccount**

## OUTPUTS

### Microsoft.ActiveDirectory.Management.ADGroup

Returns group objects that represent the security groups for the account.

## NOTES

- This cmdlet doesn't work with an Active Directory snapshot.

## RELATED LINKS

[Get-ADComputer](./Get-ADComputer.md)

[Get-ADServiceAccount](./Get-ADServiceAccount.md)

[Get-ADUser](./Get-ADUser.md)

[Search-ADAccount](./Search-ADAccount.md)

[AD DS Administration Cmdlets in Windows PowerShell](./activedirectory.md)
