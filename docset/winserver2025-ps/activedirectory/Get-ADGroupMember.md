---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
Module Name: ActiveDirectory
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/activedirectory/get-adgroupmember?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ADGroupMember
---

# Get-ADGroupMember

## SYNOPSIS
Gets the members of an Active Directory group.

## SYNTAX

```
Get-ADGroupMember [-AuthType <ADAuthType>] [-Credential <PSCredential>] [-Identity] <ADGroup>
 [-Partition <String>] [-Recursive] [-Server <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-ADGroupMember** cmdlet gets the members of an Active Directory group.
Members can be users, groups, and computers.

The *Identity* parameter specifies the Active Directory group to access.
You can identify a group by its distinguished name, GUID, security identifier, or Security Account Manager (SAM) account name.
You can also specify the group by passing a group object through the pipeline.
For example, you can use the **Get-ADGroup** cmdlet to get a group object and then pass the object through the pipeline to the Get-ADGroupMember cmdlet.

If the *Recursive* parameter is specified, the cmdlet gets all members in the hierarchy of the group that do not contain child objects.
For example, if the group SaraDavisReports contains the user KarenToh and the group JohnSmithReports, and JohnSmithReports contains the user JoshPollock, then the cmdlet returns KarenToh and JoshPollock.

For Active Directory Lightweight Directory Services (AD LDS) environments, the *Partition* parameter must be specified except in the following two conditions:

- The cmdlet is run from an Active Directory provider drive.
- A default naming context or partition is defined for the AD LDS environment.
To specify a default naming context for an AD LDS environment, set the **msDS-defaultNamingContext** property of the Active Directory directory service agent object (**nTDSDSA**) for the AD LDS instance.

## EXAMPLES

### Example 1: Get all members of a group
```
PS C:\> Get-ADGroupMember
cmdlet Get-ADGroupMember at command pipeline position 1
Supply values for the following parameters: (Type !? for Help.)
Identity: Administrators

distinguishedName : CN=Domain Admins,CN=Users,DC=Fabrikam,DC=com
name              : Domain Admins
objectClass       : group
objectGUID        : 5ccc6037-c2c9-42be-8e92-c8f98afd0011
SamAccountName    : Domain Admins
SID               : S-1-5-21-41432690-3719764436-1984117282-512

distinguishedName : CN=Enterprise Admins,CN=Users,DC=Fabrikam,DC=com
name              : Enterprise Admins
objectClass       : group
objectGUID        : 0215b0a5-aea1-40da-b598-720efe930ddf
SamAccountName    : Enterprise Admins
SID               : S-1-5-21-41432690-3719764436-1984117282-519

distinguishedName : CN=LabAdmin,CN=Users,DC=Fabrikam,DC=com
name              : LabAdmin
objectClass       : user
objectGUID        : ab7c269d-aec5-4fcc-aebe-6cd1a2e6cd53
SamAccountName    : LabAdmin
SID               : S-1-5-21-41432690-3719764436-1984117282-1000

distinguishedName : CN=Administrator,CN=Users,DC=Fabrikam,DC=com
name              : Administrator
objectClass       : user
objectGUID        : 994f46e6-c62c-483f-a6cf-124197b6a959
SamAccountName    : Administrator
SID               : S-1-5-21-41432690-3719764436-1984117282-500
```

This command gets all the members of the Administrators group.

### Example 2: Get all group members of all domain local groups
```
PS C:\> Get-ADGroup -Server localhost:60000 -Filter "GroupScope -eq 'DomainLocal'" -SearchBase "DC=AppNC" | Get-ADGroupMember -Partition "DC=AppNC"
distinguishedName : CN=SanjayPatel,OU=AccountDeptOU,DC=AppNC
name              : SanjayPatel
objectClass       : user
objectGUID        : d671de28-6e40-42a7-b32c-63d336de296d
SamAccountName    :
SID               : S-1-510474493-936115905-2231798853-1260534229-4171027843-767619944
```

This command gets the group members of all domain local groups in the AD LDS instance.

### Example 3: Get all Administrators group members
```
PS C:\> Get-ADGroupMember -Identity Administrators
distinguishedName : CN=Domain Admins,CN=Users,DC=Fabrikam,DC=com
name              : Domain Admins
objectClass       : group
objectGUID        : 5ccc6037-c2c9-42be-8e92-c8f98afd0011
SamAccountName    : Domain Admins
SID               : S-1-5-21-41432690-3719764436-1984117282-512

distinguishedName : CN=Enterprise Admins,CN=Users,DC=Fabrikam,DC=com
name              : Enterprise Admins
objectClass       : group
objectGUID        : 0215b0a5-aea1-40da-b598-720efe930ddf
SamAccountName    : Enterprise Admins
SID               : S-1-5-21-41432690-3719764436-1984117282-519

distinguishedName : CN=LabAdmin,CN=Users,DC=Fabrikam,DC=com
name              : LabAdmin
objectClass       : user
objectGUID        : ab7c269d-aec5-4fcc-aebe-6cd1a2e6cd53
SamAccountName    : LabAdmin
SID               : S-1-5-21-41432690-3719764436-1984117282-1000

distinguishedName : CN=Administrator,CN=Users,DC=Fabrikam,DC=com
name              : Administrator
objectClass       : user
objectGUID        : 994f46e6-c62c-483f-a6cf-124197b6a959
SamAccountName    : Administrator
SID               : S-1-5-21-41432690-3719764436-1984117282-500
```

This command gets all the group members of the Administrators group.

### Example 4: Get members of a group including the members of child groups
```
PS C:\> Get-ADGroupMember -Identity "Enterprise Admins" -Recursive
distinguishedName : CN=Administrator,CN=Users,DC=Fabrikam,DC=com
name              : Administrator
objectClass       : user
objectGUID        : 994f46e6-c62c-483f-a6cf-124197b6a959
SamAccountName    : Administrator
SID               : S-1-5-21-41432690-3719764436-1984117282-500

distinguishedName : CN=Sagiv Hadaya,CN=Users,DC=Fabrikam,DC=com
name              : Sagiv Hadaya
objectClass       : user
objectGUID        : 64706230-f179-4fe4-b8c9-f0d334e66ab1
SamAccountName    : SHadaya
SID               : S-1-5-21-41432690-3719764436-1984117282-1158
```

This command gets all the members of the Enterprise Admins group including the members of any child groups.

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
The default credentials are the credentials of the currently logged on user unless the cmdlet is run from an Active Directory module for Windows PowerShell provider drive.
If the cmdlet is run from such a provider drive, the account associated with the drive is the default.

To specify this parameter, you can type a user name, such as User1 or Domain01\User01 or you can specify a **PSCredential** object.
If you specify a user name for this parameter, the cmdlet prompts for a password.

You can also create a **PSCredential** object by using a script or by using the **Get-Credential** cmdlet.
You can then set the *Credential* parameter to the **PSCredential** object.

If the acting credentials do not have directory-level permission to perform the task, Active Directory module for Windows PowerShell returns a terminating error.

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
Specifies an Active Directory group object by providing one of the following values.
The identifier in parentheses is the LDAP display name for the attribute.
The acceptable values for this parameter are:

- A distinguished name
- A GUID (objectGUID)
- A security identifier (objectSid)
- A Security Account Manager account name (sAMAccountName)

The cmdlet searches the default naming context or partition to find the object.
If two or more objects are found, the cmdlet returns a non-terminating error.

This parameter can also get this object through the pipeline or you can set this parameter to an object instance.

```yaml
Type: ADGroup
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
The cmdlet searches this partition to find the object defined by the *Identity* parameter.

In many cases, a default value is used for the *Partition* parameter if no value is specified.
The rules for determining the default value are given below.
Note that rules listed first are evaluated first and once a default value can be determined, no further rules are evaluated.

In Active Directory Domain Services (AD DS) environments, a default value for *Partition* is set in the following cases:

- If the *Identity* parameter is set to a distinguished name, the default value of *Partition* is automatically generated from this distinguished name.
- If running cmdlets from an Active Directory provider drive, the default value of *Partition* is automatically generated from the current path in the drive.
- If none of the previous cases apply, the default value of *Partition* is set to the default partition or naming context of the target domain.

In Active Directory Lightweight Directory Services (AD LDS) environments, a default value for *Partition* is set in the following cases:

- If the *Identity* parameter is set to a distinguished name, the default value of *Partition* is automatically generated from this distinguished name.
- If running cmdlets from an Active Directory provider drive, the default value of *Partition* is automatically generated from the current path in the drive.
- If the target AD LDS instance has a default naming context, the default value of *Partition* is set to the default naming context.
To specify a default naming context for an AD LDS environment, set the **msDS-defaultNamingContext** property of the Active Directory directory service agent object (**nTDSDSA**) for the AD LDS instance.
- If none of the previous cases apply, the *Partition* parameter does not take a default value.

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

### -Recursive
Specifies that the cmdlet get all members in the hierarchy of a group that do not contain child objects.

If the specified group does not have any members, then nothing is returned.

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

### -Server
Specifies the AD DS instance to connect to, by providing one of the following values for a corresponding domain name or directory server.
The service may be any of the following: AD LDS, AD DS, or Active Directory snapshot instance.

Specify the AD DS instance in one of the following ways:

Domain name values:

- Fully qualified domain name
- NetBIOS name

Directory server values:

- Fully qualified directory server name
- NetBIOS name
- Fully qualified directory server name and port

The default value for this parameter is determined by one of the following methods in the order that they are listed:

- By using the *Server* value from objects passed through the pipeline
- By using the server information associated with the AD DS Windows PowerShell provider drive, when the cmdlet runs in that drive
- By using the domain of the computer running Windows PowerShell

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

### None or Microsoft.ActiveDirectory.Management.ADGroup
A group object is received by the *Identity* parameter.

## OUTPUTS

### Microsoft.ActiveDirectory.Management.ADPrincipal
Returns one or more principal objects that represent users, computers or groups that are members of the specified group.

## NOTES
* This cmdlet does not work with an Active Directory snapshot.
* This cmdlet does not work when a group has members located in a different forest, and the forest does not have Active Directory Web Service running.

## RELATED LINKS

[Add-ADGroupMember](./Add-ADGroupMember.md)

[Add-ADPrincipalGroupMembership](./Add-ADPrincipalGroupMembership.md)

[Get-ADGroup](./Get-ADGroup.md)

[Get-ADPrincipalGroupMembership](./Get-ADPrincipalGroupMembership.md)

[Remove-ADGroupMember](./Remove-ADGroupMember.md)

[Remove-ADPrincipalGroupMembership](./Remove-ADPrincipalGroupMembership.md)

