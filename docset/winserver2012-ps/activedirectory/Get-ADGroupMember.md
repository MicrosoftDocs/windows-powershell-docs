---
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
ms.assetid: A308681E-8EA3-42EE-9241-11101F6962C3
manager: dansimp
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
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
The Get-ADGroupMember cmdlet gets the members of an Active Directory group.
Members can be users, groups, and computers.

The Identity parameter specifies the Active Directory group to access.
You can identify a group by its distinguished name (DN), GUID, security identifier (SID), or Security Accounts Manager (SAM) account name.
You can also specify the group by passing a group object through the pipeline.
For example, you can use the Get-ADGroup cmdlet to retrieve a group object and then pass the object through the pipeline to the Get-ADGroupMember cmdlet.

If the Recursive parameter is specified, the cmdlet gets all members in the hierarchy of the group that do not contain child objects.
For example, if the group SaraDavisReports contains the user KarenToh and the group JohnSmithReports, and JohnSmithReports contains the user JoshPollock, then the cmdlet returns KarenToh and JoshPollock.

For AD LDS environments, the Partition parameter must be specified except in the following two conditions:

-The cmdlet is run from an Active Directory provider drive.

-A default naming context or partition is defined for the AD LDS environment.
To specify a default naming context for an AD LDS environment, set the msDS-defaultNamingContext property of the Active Directory directory service agent (DSA) object (nTDSDSA) for the AD LDS instance.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
C:\PS>get-adgroupmember
cmdlet Get-ADGroupMember at command pipeline position 1
Supply values for the following parameters:
(Type !? for Help.)
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

Description

-----------

Get all the members of the administrators groups using the default behavior.

### -------------------------- EXAMPLE 2 --------------------------
```
C:\PS>get-adgroup -server localhost:60000 -filter "GroupScope -eq 'DomainLocal'" -SearchBase "DC=AppNC" | get-adgroupmember -partition "DC=AppNC"

distinguishedName : CN=SanjayPatel,OU=AccountDeptOU,DC=AppNC
name              : SanjayPatel
objectClass       : user
objectGUID        : d671de28-6e40-42a7-b32c-63d336de296d
SamAccountName    :
SID               : S-1-510474493-936115905-2231798853-1260534229-4171027843-767619944
```

Description

-----------

Get the groups members of all domain local groups in the AD LDS instance.

### -------------------------- EXAMPLE 3 --------------------------
```
C:\PS>get-adgroupmember -Identity administrators

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

Description

-----------

Get all the group  members of the administrators group.

### -------------------------- EXAMPLE 4 --------------------------
```
C:\PS>get-adgroupmember "Enterprise Admins" -recursive

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

Description

-----------

Get all the members of the 'Enterprise Admins' group including the members of any child groups.

## PARAMETERS

### -AuthType
Specifies the authentication method to use.
Possible values for this parameter include:

Negotiate or 0

Basic or 1

The default authentication method is Negotiate.

A Secure Sockets Layer (SSL) connection is required for the Basic authentication method.

The following example shows how to set this parameter to Basic.

-AuthType Basic

```yaml
Type: ADAuthType
Parameter Sets: (All)
Aliases: 
Accepted values: Negotiate, Basic

Required: False
Position: Named
Default value: Microsoft.ActiveDirectory.Management.AuthType.Negotiate
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
Specifies the user account credentials to use to perform this task.
The default credentials are the credentials of the currently logged on user unless the cmdlet is run from an Active Directory PowerShell provider drive.
If the cmdlet is run from such a provider drive, the account associated with the drive is the default.

To specify this parameter, you can type a user name, such as "User1" or "Domain01\User01" or you can specify a PSCredential object.
If you specify a user name for this parameter, the cmdlet prompts for a password.

You can also create a PSCredential object by using a script or by using the Get-Credential cmdlet.
You can then set the Credential parameter to the PSCredential object The following example shows how to create credentials.

$AdminCredentials = Get-Credential "Domain01\User01"

The following shows how to set the Credential parameter to these credentials.

-Credential $AdminCredentials

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
Specifies an Active Directory group object by providing one of the following values.
The identifier in parentheses is the LDAP display name for the attribute.

Distinguished Name

Example: CN=saradavisreports,OU=europe,CN=users,DC=corp,DC=contoso,DC=com

GUID (objectGUID)

Example: 599c3d2e-f72d-4d20-8a88-030d99495f20

Security Identifier (objectSid)

Example: S-1-5-21-3165297888-301567370-576410423-1103

Security Accounts Manager (SAM) Account Name (sAMAccountName)

Example: saradavisreports

The cmdlet searches the default naming context or partition to find the object.
If two or more objects are found, the cmdlet returns a non-terminating error.

This parameter can also get this object through the pipeline or you can set this parameter to an object instance.

This example shows how to set the parameter to a distinguished name.

-Identity  "CN=saradavisreports,OU=europe,CN=users,DC=corp,DC=contoso,DC=com"

This example shows how to set this parameter to a group object instance named "ADGroupInstance".

-Identity $ADGroupInstance

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
The cmdlet searches this partition to find the object defined by the Identity parameter.

The following two examples show how to specify a value for this parameter.

-Partition "CN=Configuration,DC=EUROPE,DC=TEST,DC=CONTOSO,DC=COM"

-Partition "CN=Schema,CN=Configuration,DC=EUROPE,DC=TEST,DC=CONTOSO,DC=COM"

In many cases, a default value will be used for the Partition parameter if no value is specified. 
The rules for determining the default value are given below. 
Note that rules listed first are evaluated first and once a default value can be determined, no further rules will be evaluated.

In AD DS environments, a default value for Partition will be set in the following cases:  - If the Identity parameter is set to a distinguished name, the default value of Partition is automatically generated from this distinguished name.

- If running cmdlets from an Active Directory provider drive, the default value of Partition is automatically generated from the current path in the drive.
- If none of the previous cases apply, the default value of Partition will be set to the default partition or naming context of the target domain.

In AD LDS environments, a default value for Partition will be set in the following cases:

- If the Identity parameter is set to a distinguished name, the default value of Partition is automatically generated from this distinguished name.
- If running cmdlets from an Active Directory provider drive, the default value of Partition is automatically generated from the current path in the drive.
- If the target AD LDS instance has a default naming context, the default value of Partition will be set to the default naming context.  To specify a default naming context for an AD LDS environment, set the msDS-defaultNamingContext property of the Active Directory directory service agent (DSA) object (nTDSDSA) for the AD LDS instance.
- If none of the previous cases apply, the Partition parameter will not take any default value.

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
The following example shows a hierarchy for the group SaraDavisReports.

+SaraDavisReports \[group\]

-KarenToh \[user\]

-MattHinkLaptop \[computer\]

+JohnSmithReports \[group\]

-JoshPollock \[user\]

-ArmandoPinto \[user\]

+JohnSmithComputers \[group\]

-JoshComputer \[computer\]

If you specify SaraDavisReports as the group and specify the Recursive parameter, the following members and sub-members are returned.

KarenToh

MattHinkLaptop

JoshPollock

ArmandoPinto

JoshComputer

If the specified group does not have any members, then nothing is returned.

The following example shows how to specify this parameter.

-Recursive

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
Specifies the Active Directory Domain Services instance to connect to, by providing one of the following values for a corresponding domain name or directory server.
The service may be any of the following:  Active Directory Lightweight Domain Services, Active Directory Domain Services or Active Directory Snapshot instance.

Domain name values:

Fully qualified domain name

Examples: corp.contoso.com

NetBIOS name

Example: CORP

Directory server values:

Fully qualified directory server name

Example: corp-DC12.corp.contoso.com

NetBIOS name

Example: corp-DC12

Fully qualified directory server name and port

Example: corp-DC12.corp.contoso.com:3268

The default value for the Server parameter is determined by one of the following methods in the order that they are listed:

-By using Server value from objects passed through the pipeline.

-By using the server information associated with the Active Directory PowerShell provider drive, when running under that drive.

-By using the domain of the computer running Windows PowerShell.

The following example shows how to specify a full qualified domain name as the parameter value.

-Server "corp.contoso.com"

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None or Microsoft.ActiveDirectory.Management.ADGroup
A group object is received by the Identity parameter

## OUTPUTS

### Microsoft.ActiveDirectory.Management.ADPrincipal
Returns one or more principal objects that represent users, computers or groups that are members of the specified group.

## NOTES
* This cmdlet does not work with an Active Directory Snapshot.

  This cmdlet does not work when a group has members located in a different forest, and the forest does not have Active Directory Web Service running.

## RELATED LINKS

[Add-ADGroupMember](./Add-ADGroupMember.md)

[Add-ADPrincipalGroupMembership](./Add-ADPrincipalGroupMembership.md)

[Get-ADGroup](./Get-ADGroup.md)

[Get-ADPrincipalGroupMembership](./Get-ADPrincipalGroupMembership.md)

[Remove-ADGroupMember](./Remove-ADGroupMember.md)

[Remove-ADPrincipalGroupMembership](./Remove-ADPrincipalGroupMembership.md)

