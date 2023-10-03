---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
Module Name: ActiveDirectory
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/activedirectory/get-adprincipalgroupmembership?view=windowsserver2016-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ADPrincipalGroupMembership
---

# Get-ADPrincipalGroupMembership

## SYNOPSIS
Gets the Active Directory groups that have a specified user, computer, group, or service account.

## SYNTAX

```
Get-ADPrincipalGroupMembership [-AuthType <ADAuthType>] [-Credential <PSCredential>] [-Identity] <ADPrincipal>
 [-Partition <String>] [-ResourceContextPartition <String>] [-ResourceContextServer <String>]
 [-Server <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-ADPrincipalGroupMembership** cmdlet gets the Active Directory groups that have a specified user, computer, group, or service account as a member.
This cmdlet requires a global catalog to perform the group search.
If the forest that contains the user, computer, or group does not have a global catalog, the cmdlet returns a non-terminating error.
If you want to search for local groups in another domain, use the *ResourceContextServer* parameter to specify the alternate server in the other domain.

The *Identity* parameter specifies the user, computer, or group object that you want to determine group membership for.
You can identify a user, computer, or group object by its distinguished name, GUID, security identifier, or SAM account name.
You can also specify a user, group, or computer object variable, such as `$<localGroupObject>`, or pass an object through the pipeline to the *Identity* parameter.
For example, you can use the **Get-ADGroup** cmdlet to retrieve a group object and then pass the object through the pipeline to the Get-ADPrincipalGroupMembership cmdlet.
Similarly, you can use **Get-ADUser** or **Get-ADComputer** to get user and computer objects to pass through the pipeline.

For Active Directory Lightweight Directory Services (AD LDS) environments, the *Partition* parameter must be specified except in the following two conditions:

- The cmdlet is run from an Active Directory provider drive.
- A default naming context or partition is defined for the AD LDS environment.
To specify a default naming context for an AD LDS environment, set the **msDS-defaultNamingContext** property of the Active Directory directory service agent  object (**nTDSDSA**) for the AD LDS instance.

## EXAMPLES

### Example 1: Get group memberships for a user in an AD LDS instance
```
PS C:\> Get-ADPrincipalGroupMembership -Server localhost:60000 -Identity "CN=DavidChew,DC=AppNC" -Partition "DC=AppNC"
```

This command gets all of the group memberships for the user CN=DavidChew,DC=AppNC in an AD LDS instance.

### Example 2: Get group memberships for the Administrator
```
PS C:\> Get-ADPrincipalGroupMembership -Identity Administrator


distinguishedName : CN=Domain Users,CN=Users,DC=Fabrikam,DC=com
GroupCategory     : Security
GroupScope        : Global
name              : Domain Users
objectClass       : group
objectGUID        : 86c0f0d5-8b4d-4f35-a867-85a006b92902
SamAccountName    : Domain Users
SID               : S-1-5-21-41432690-3719764436-1984117282-513

distinguishedName : CN=Administrators,CN=Builtin,DC=Fabrikam,DC=com
GroupCategory     : Security
GroupScope        : DomainLocal
name              : Administrators
objectClass       : group
objectGUID        : 02ce3874-dd86-41ba-bddc-013f34019978
SamAccountName    : Administrators
SID               : S-1-5-32-544

distinguishedName : CN=Schema Admins,CN=Users,DC=Fabrikam,DC=com
GroupCategory     : Security
GroupScope        : Universal
name              : Schema Admins
objectClass       : group
objectGUID        : 8d62890f-385e-4cfa-9b2a-c72576097583
SamAccountName    : Schema Admins
SID               : S-1-5-21-41432690-3719764436-1984117282-518

distinguishedName : CN=Enterprise Admins,CN=Users,DC=Fabrikam,DC=com
GroupCategory     : Security
GroupScope        : Universal
name              : Enterprise Admins
objectClass       : group
objectGUID        : 0215b0a5-aea1-40da-b598-720efe930ddf
SamAccountName    : Enterprise Admins
SID               : S-1-5-21-41432690-3719764436-1984117282-519

distinguishedName : CN=Domain Admins,CN=Users,DC=Fabrikam,DC=com
GroupCategory     : Security
GroupScope        : Global
name              : Domain Admins
objectClass       : group
objectGUID        : 5ccc6037-c2c9-42be-8e92-c8f98afd0011
SamAccountName    : Domain Admins
SID               : S-1-5-21-41432690-3719764436-1984117282-512

distinguishedName : CN=Group Policy Creator Owners,CN=Users,DC=Fabrikam,DC=com
GroupCategory     : Security
GroupScope        : Global
name              : Group Policy Creator Owners
objectClass       : group
objectGUID        : a58f7bf2-fd20-4bbd-96f0-ee10fa1613c7
SamAccountName    : Group Policy Creator Owners
SID               : S-1-5-21-41432690-3719764436-1984117282-520
```

This command gets all the group memberships for the Administrator.

### Example 3: Get group memberships for an account in a resource domain
```
PS C:\> Get-ADPrincipalGroupMembership -Identity Administrator -ResourceContextServer ChildDomain.Fabrikam.Com -ResourceContextPartition "DC=Fabrikam,DC=com"


distinguishedName : CN=Domain Users,CN=Users,DC=Fabrikam,DC=com
GroupCategory     : Security
GroupScope        : Global
name              : Domain Users
objectClass       : group
objectGUID        : 86c0f0d5-8b4d-4f35-a867-85a006b92902
SamAccountName    : Domain Users
SID               : S-1-5-21-41432690-3719764436-1984117282-513

distinguishedName : CN=Group Policy Creator Owners,CN=Users,DC=Fabrikam,DC=com
GroupCategory     : Security
GroupScope        : Global
name              : Group Policy Creator Owners
objectClass       : group
objectGUID        : a58f7bf2-fd20-4bbd-96f0-ee10fa1613c7
SamAccountName    : Group Policy Creator Owners
SID               : S-1-5-21-41432690-3719764436-1984117282-520

distinguishedName : CN=Enterprise Admins,CN=Users,DC=Fabrikam,DC=com
GroupCategory     : Security
GroupScope        : Universal
name              : Enterprise Admins
objectClass       : group
objectGUID        : 0215b0a5-aea1-40da-b598-720efe930ddf
SamAccountName    : Enterprise Admins
SID               : S-1-5-21-41432690-3719764436-1984117282-519

distinguishedName : CN=Schema Admins,CN=Users,DC=Fabrikam,DC=com
GroupCategory     : Security
GroupScope        : Universal
name              : Schema Admins
objectClass       : group
objectGUID        : 8d62890f-385e-4cfa-9b2a-c72576097583
SamAccountName    : Schema Admins
SID               : S-1-5-21-41432690-3719764436-1984117282-518

distinguishedName : CN=Domain Admins,CN=Users,DC=Fabrikam,DC=com
GroupCategory     : Security
GroupScope        : Global
name              : Domain Admins
objectClass       : group
objectGUID        : 5ccc6037-c2c9-42be-8e92-c8f98afd0011
SamAccountName    : Domain Admins
SID               : S-1-5-21-41432690-3719764436-1984117282-512

distinguishedName : CN=Administrators,CN=Builtin,DC=Fabrikam,DC=com
GroupCategory     : Security
GroupScope        : DomainLocal
name              : Administrators
objectClass       : group
objectGUID        : 02ce3874-dd86-41ba-bddc-013f34019978
SamAccountName    : Administrators
SID               : S-1-5-32-544
```

This command gets all of the group memberships for the Administrator account in the local domain in the resource domain ChildDomain.Fabrikam.Com.

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
Specifies the user account credentials to use to perform this task.
The default credentials are the credentials of the currently logged on user unless the cmdlet is run from an Active Directory PowerShell provider drive.
If the cmdlet is run from such a provider drive, the account associated with the drive is the default.

To specify this parameter, you can type a user name, such as User1 or Domain01\User01 or you can specify a **PSCredential** object.
If you specify a user name for this parameter, the cmdlet prompts for a password.

You can also create a **PSCredential** object by using a script or by using the **Get-Credential** cmdlet.
You can then set the *Credential* parameter to the **PSCredential** object.

If the acting credentials do not have directory-level permission to perform the task, Active Directory PowerShell returns a terminating error.

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
Specifies an Active Directory principal object by providing one of the following property values.
The identifier in parentheses is the Lightweight Directory Access Protocol (LDAP) display name for the attribute.
The acceptable values for this parameter are:

- A distinguished name
- A GUID (objectGUID) 
- A security identifier (objectSid) 
- A SAM account name (sAMAccountName)

The cmdlet searches the default naming context or partition to find the object.
If two or more objects are found, the cmdlet returns a non-terminating error.

This parameter can also get this object through the pipeline or you can set this parameter to an object instance.

Derived types, such as the following are also accepted:

- **Microsoft.ActiveDirectory.Management.ADGroup**
- **Microsoft.ActiveDirectory.Management.ADUser**
- **Microsoft.ActiveDirectory.Management.ADComputer**
- **Microsoft.ActiveDirectory.Management.ADServiceAccount**

```yaml
Type: ADPrincipal
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Partition
Specifies the distinguished name of an Active Directory partition.
The distinguished name must be one of the naming contexts on the current directory server.
The cmdlet searches this partition to find the object defined by the **Identity** parameter.

In many cases, a default value is used for the **Partition** parameter if no value is specified.
The rules for determining the default value are given below.
Note that rules listed first are evaluated first and once a default value can be determined, no further rules are evaluated.

In Active Directory Domain Services (AD DS) environments, a default value for **Partition** is set in the following cases: 

- If the **Identity** parameter is set to a distinguished name, the default value of **Partition** is automatically generated from this distinguished name.
- If running cmdlets from an Active Directory provider drive, the default value of **Partition** is automatically generated from the current path in the drive. 
- If none of the previous cases apply, the default value of **Partition** is set to the default partition or naming context of the target domain.

In Active Directory Lightweight Directory Services (AD LDS) environments, a default value for **Partition** is set in the following cases:

- If the **Identity** parameter is set to a distinguished name, the default value of **Partition** is automatically generated from this distinguished name. 
- If running cmdlets from an Active Directory provider drive, the default value of **Partition** is automatically generated from the current path in the drive. 
- If the target AD LDS instance has a default naming context, the default value of **Partition** is set to the default naming context.
To specify a default naming context for an AD LDS environment, set the **msDS-defaultNamingContext** property of the Active Directory directory service agent object (**nTDSDSA**) for the AD LDS instance. 
- If none of the previous cases apply, the **Partition** parameter does not take any default value.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: DefaultNC; Provider: The default is to use the Partition that you are currently in. Otherwise, use DefaultNC (that is, if you are in the RootDSE)
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceContextPartition
Specifies the distinguished name of the partition of an AD or AD LDS instance to search.
Use this parameter with the *ResourceContextServer* parameter to specify a partition hosted by the specified server.
If the *ResourceContextPartition* parameter is not specified, the default partition of the *ResourceContextServer* is searched.

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

### -ResourceContextServer
Specifies that the cmdlet return a list of groups that the user is a member of and that reside in the specified domain.
Use this parameter to search for groups in a domain that is not the domain where the user's account resides.
To search a partition other than the default partition in this domain, also specify the *ResourceContextPartition* parameter.

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

### -Server
The default authentication method is Negotiate.

A Secure Sockets Layer (SSL) connection is required for the Basic authentication method.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.ActiveDirectory.Management.ADPrincipal
A principal object that represents a user, computer or group is received by the *Identity* parameter.
Derived types, such as the following are also received by this parameter:

- **Microsoft.ActiveDirectory.Management.ADUser**
- **Microsoft.ActiveDirectory.Management.ADComputer**
- **Microsoft.ActiveDirectory.Management.ADServiceAccount**
- **Microsoft.ActiveDirectory.Management.ADGroup**

## OUTPUTS

### Microsoft.ActiveDirectory.Management.ADGroup
Returns group objects that have the specified user, computer, group or service account as a member.

The **Get-ADPrincipalGroupMembership** cmdlet returns a default set of **ADGroup** property values.
To retrieve additional **ADGroup** properties pass the **ADGroups** objects produced by this cmdlet through the pipline to **Get-ADGroup**. 
Specify the additional properties required from the group objects by passing the -Properties parameter to **Get-ADGroup**.

## NOTES
* This cmdlet does not work with an Active Directory snapshot.

## RELATED LINKS

[Add-ADGroupMember](./Add-ADGroupMember.md)

[Add-ADPrincipalGroupMembership](./Add-ADPrincipalGroupMembership.md)

[Get-ADComputer](./Get-ADComputer.md)

[Get-ADGroup](./Get-ADGroup.md)

[Get-ADGroupMember](./Get-ADGroupMember.md)

[Get-ADUser](./Get-ADUser.md)

[Remove-ADGroupMember](./Remove-ADGroupMember.md)

[Remove-ADPrincipalGroupMembership](./Remove-ADPrincipalGroupMembership.md)

