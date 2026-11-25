---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
Module Name: ActiveDirectory
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/activedirectory/add-adgroupmember?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-ADGroupMember
---

# Add-ADGroupMember

## SYNOPSIS
Adds one or more members to an Active Directory group.

## SYNTAX

```
Add-ADGroupMember [-WhatIf] [-Confirm] [-AuthType <ADAuthType>]
 [-Credential <PSCredential>] [-Identity] <ADGroup> [-Members] <ADPrincipal[]>
 [-MemberTimeToLive <TimeSpan>] [-Partition <String>] [-PassThru] [-Server <String>]
 [-DisablePermissiveModify] [<CommonParameters>]
```

## DESCRIPTION

The `Add-ADGroupMember` cmdlet adds one or more users, groups, service accounts, or computers as
new members of an Active Directory group.

The **Identity** parameter specifies the Active Directory group that receives the new members. You
can identify a group by its distinguished name, GUID, security identifier, or Security Account
Manager (SAM) account name. You can also specify group object variable, such as
`$<localGroupObject>`, or pass a group object through the pipeline to the **Identity** parameter.
For example, you can use the `Get-ADGroup` cmdlet to get a group object and then pass the object
through the pipeline to the `Add-ADGroupMember` cmdlet.

The **Members** parameter specifies the new members to add to a group. You can identify a new member
by its distinguished name, GUID, security identifier, or SAM account name. You can also specify
user, computer, and group object variables, such as `$<localUserObject>`. If you are specifying more
than one new member, use a comma-separated list. You cannot pass user, computer, or group objects
through the pipeline to this cmdlet. To add user, computer, or group objects to a group by using the
pipeline, use the `Add-ADPrincipalGroupMembership` cmdlet.

For Active Directory Lightweight Directory Services (AD LDS) environments, the **Partition**
parameter must be specified except in the following two conditions:

- The cmdlet is run from an Active Directory provider drive.
- A default naming context or partition is defined for the AD LDS environment.
- To specify a default naming context for an AD LDS environment, set the
  **msDS-defaultNamingContext** property of the Active Directory directory service agent object
  (nTDSDSA) for the AD LDS instance.

## EXAMPLES

### EXAMPLE 1

```powershell
Add-ADGroupMember -Identity SvcAccPSOGroup -Members SQL01, SQL02
```

This command adds the user accounts with the SAM account names `SQL01` and `SQL02` to the group
`SvcAccPSOGroup`.

### EXAMPLE 2

```powershell
$params = @{
    Server = 'localhost:60000'
    SearchBase = 'OU=AccountDeptOU,DC=AppNC'
    Filter = "name -like 'AccountLeads'"
}
Get-ADGroup @params |
    Add-ADGroupMember -Members 'CN=PattiFuller,OU=AccountDeptOU,DC=AppNC'
```

This command gets a group from the organizational unit `OU=AccountDeptOU,DC=AppNC` in the AD LDS
instance `localhost:60000` that has the name `AccountLeads`, and then pipes it to
`Add-ADGroupMember`, which then adds the user account with the distinguished name
`CN=PattiFuller,OU=AccountDeptOU,DC=AppNC` to it.

### EXAMPLE 3

```powershell
$userParams = @{
    Identity = 'CN=Chew David,OU=UserAccounts,DC=NORTHAMERICA,DC=FABRIKAM,DC=COM'
    Server = 'northamerica.fabrikam.com'
}
$User = Get-ADUser @userParams
$groupParams = @{
    Identity = 'CN=AccountLeads,OU=UserAccounts,DC=EUROPE,DC=FABRIKAM,DC=COM'
    Server = 'europe.fabrikam.com'
}
$Group = Get-ADGroup @groupParams
Add-ADGroupMember -Identity $Group -Members $User -Server "europe.fabrikam.com"
```

This command adds the user `CN=Chew David,OU=UserAccounts` from the North America domain to the
group `CN=AccountLeads,OU=UserAccounts` in the Europe domain.

## PARAMETERS

### -AuthType

Specifies the authentication method to use. The acceptable values for this parameter are:

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

### -DisablePermissiveModify

Group membership updates use permissive modify by default. This suppresses an error when adding a
member that is already member of the group. When this parameter is used, an error "The specified
account name is already a member of the group" is returned.

This parameter is available in Windows Server 2019 with the September 2020 Updates.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Identity

Specifies an Active Directory group object by providing one of the following values. The identifier
in parentheses is the Lightweight Directory Access Protocol (LDAP) display name for the attribute.
The acceptable values for this parameter are:

- A distinguished name
- A GUID (**objectGUID**)
- A security identifier (**objectSid**)
- Security Accounts Manager account name (**sAMAccountName**)

The cmdlet searches the default naming context or partition to find the object. If two or more
objects are found, the cmdlet returns a non-terminating error.

This parameter can also get this object through the pipeline or you can set this parameter to an
object instance.

```yaml
Type: Microsoft.ActiveDirectory.Management.ADGroup
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -MemberTimeToLive

Specifies a Time to Live (TTL) for the new group members.

```yaml
Type: System.TimeSpan
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Members

Specifies an array of user, group, and computer objects in a comma-separated list to add to a group.
To identify each object, use one of the following property values. The identifier in parentheses is
the LDAP display name. The acceptable values for this parameter are:

- Distinguished name
- GUID (**objectGUID**)
- Security identifier (**objectSid**)
- SAM account name (**sAMAccountName**)

You can also provide objects to this parameter directly.

The following examples show how to specify this parameter.

This example specifies a user and group to add by specifying the distinguished name and the SAM
account name properties.

`-Members "CN=SaraDavis,CN=employees,CN=Users,DC=contoso,DC=com", "saradavisreports"`

This example specifies a user and a group object that are defined in the current Windows PowerShell
session as input for the parameter.

`-Members $userObject, $GroupObject`

The objects specified for this parameter are processed as
**Microsoft.ActiveDirectory.Management.ADPrincipal** objects. Derived types, such as the following
are also received by this parameter.

- **Microsoft.ActiveDirectory.Management.ADUser**
- **Microsoft.ActiveDirectory.Management.ADComputer**
- **Microsoft.ActiveDirectory.Management.ADServiceAccount**
- **Microsoft.ActiveDirectory.Management.ADGroup**

You cannot pass objects through the pipeline to this parameter.

```yaml
Type: Microsoft.ActiveDirectory.Management.ADPrincipal[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
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

### -PassThru

Returns an object representing the item with which you're working. By default, this cmdlet doesn't
generate any output.

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

### -WhatIf

Shows what would happen if the cmdlet runs. The cmdlet isn't run.

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

### Microsoft.ActiveDirectory.Management.ADGroup

A group object is received by the **Identity** parameter.

## OUTPUTS

### None or Microsoft.ActiveDirectory.Management.ADGroup

Returns the modified group object when the **PassThru** parameter is specified. By default, this
cmdlet does not generate any output.

## NOTES

- This cmdlet does not work with a read-only domain controller.
- This cmdlet does not work with an Active Directory snapshot.
- This cmdlet will allow you to add a group as a member of itself which could lead to unstable
  behavior.

## RELATED LINKS

[Add-ADPrincipalGroupMembership](./Add-ADPrincipalGroupMembership.md)

[Get-ADGroup](./Get-ADGroup.md)

[Get-ADGroupMember](./Get-ADGroupMember.md)

[Get-ADPrincipalGroupMembership](./Get-ADPrincipalGroupMembership.md)

[Remove-ADGroupMember](./Remove-ADGroupMember.md)

[Remove-ADPrincipalGroupMembership](./Remove-ADPrincipalGroupMembership.md)
