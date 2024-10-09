---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
Module Name: ActiveDirectory
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/activedirectory/get-adgroup?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ADGroup
---

# Get-ADGroup

## SYNOPSIS
Gets one or more Active Directory groups.

## SYNTAX

### Filter (Default)
```
Get-ADGroup [-AuthType <ADAuthType>] [-Credential <PSCredential>] -Filter <String> [-Properties <String[]>]
 [-ResultPageSize <Int32>] [-ResultSetSize <Int32>] [-SearchBase <String>] [-SearchScope <ADSearchScope>]
 [-Server <String>] [-ShowMemberTimeToLive] [<CommonParameters>]
```

### Identity
```
Get-ADGroup [-AuthType <ADAuthType>] [-Credential <PSCredential>] [-Identity] <ADGroup> [-Partition <String>]
 [-Properties <String[]>] [-Server <String>] [-ShowMemberTimeToLive] [<CommonParameters>]
```

### LdapFilter
```
Get-ADGroup [-AuthType <ADAuthType>] [-Credential <PSCredential>] -LDAPFilter <String> [-Properties <String[]>]
 [-ResultPageSize <Int32>] [-ResultSetSize <Int32>] [-SearchBase <String>] [-SearchScope <ADSearchScope>]
 [-Server <String>] [-ShowMemberTimeToLive] [<CommonParameters>]
```

## DESCRIPTION
The **Get-ADGroup** cmdlet gets a group or performs a search to retrieve multiple groups from an Active Directory.

The *Identity* parameter specifies the Active Directory group to get.
You can identify a group by its distinguished name (DN), GUID, security identifier (SID), or Security Accounts Manager (SAM) account name.
You can also specify group object variable, such as `$<localGroupObject>`.

To search for and retrieve more than one group, use the *Filter* or *LDAPFilter* parameters.
The *Filter* parameter uses the PowerShell Expression Language to write query strings for Active Directory.
PowerShell Expression Language syntax provides rich type conversion support for value types received by the *Filter* parameter.
For more information about the *Filter* parameter syntax, type `Get-Help about_ActiveDirectory_Filter`.
If you have existing Lightweight Directory Access Protocol (LDAP) query strings, you can use the *LDAPFilter* parameter.

This cmdlet gets a default set of group object properties.
To get additional properties use the *Properties* parameter.
For more information about the how to determine the properties for group objects, see the *Properties* parameter description.

## EXAMPLES

### Example 1: Get a group by SAM account name
```
PS C:\> Get-ADGroup -Identity Administrators
DistinguishedName : CN=Administrators,CN=Builtin,DC=Fabrikam,DC=com
GroupCategory     : Security
GroupScope        : DomainLocal
Name              : Administrators
ObjectClass       : group
ObjectGUID        : 02ce3874-dd86-41ba-bddc-013f34019978
SamAccountName    : Administrators
SID               : S-1-5-32-544
```

This command gets the group with the SAM account name Administrators.

### Example 2: Get a group by SID
```
PS C:\> Get-ADGroup -Identity S-1-5-32-544 -Properties member
DistinguishedName : CN=Administrators,CN=Builtin,DC=Fabrikam,DC=com
GroupCategory     : Security
GroupScope        : DomainLocal
member            : {CN=Domain Admins,CN=Users,DC=Fabrikam,DC=com, CN=Enterprise Admins,CN=Users,DC=Fabrikam,DC=com, CN=LabAdmin,CN=Users,DC=Fabrikam,DC=com, C
N=Administrator,CN=Users,DC=Fabrikam,DC=com}
Name              : Administrators
ObjectClass       : group
ObjectGUID        : 02ce3874-dd86-41ba-bddc-013f34019978
SamAccountName    : Administrators
SID               : S-1-5-32-544
```

This command gets the group with SID S-1-5-32-544 and the property member.

### Example 3: Get a group and filter the results
```
PS C:\> Get-ADGroup -Filter 'GroupCategory -eq "Security" -and GroupScope -ne "DomainLocal"'
```

This command gets all groups that have a GroupCategory of Security but do not have a GroupScope of DomainLocal.

### Example 4: Get a group from a specified search base and filter the results
```
PS C:\> Get-ADGroup -Server localhost:60000 -Filter "GroupScope -eq 'DomainLocal'" -SearchBase "DC=AppNC"


DistinguishedName : CN=AlphaGroup,OU=AccountDeptOU,DC=AppNC
GroupCategory     : Security
GroupScope        : DomainLocal
Name              : AlphaGroup
ObjectClass       : group
ObjectGUID        : 6498c9fb-7c62-48fe-9972-1461f7f3dec2
SID               : S-1-510474493-936115905-2475435479-1276657127-1006239422-938965137

DistinguishedName : CN=BranchOffice1,OU=AccountDeptOU,DC=AppNC
GroupCategory     : Security
GroupScope        : DomainLocal
Name              : BranchOffice1
ObjectClass       : group
ObjectGUID        : 0b7504c5-482b-4a73-88f5-8a76960e4568
SID               : S-1-510474493-936115905-2534227223-1194883713-3669005192-3746664089

DistinguishedName : CN=AccountLeads,OU=AccountDeptOU,DC=AppNC
GroupCategory     : Distribution
GroupScope        : DomainLocal
Name              : AccountLeads
ObjectClass       : group
ObjectGUID        : b20c032b-2de9-401a-b48c-341854a37254
SID               : S-1-510474493-936115905-2813670187-1179675302-2001457839-270172950
```

This command gets all the DomainLocal groups from the AppNC partition of the AD LDS instance.

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

### -Filter
Specifies a query string that retrieves Active Directory objects.
This string uses the PowerShell Expression Language syntax.
The PowerShell Expression Language syntax provides rich type-conversion support for value types received by the *Filter* parameter.
The syntax uses an in-order representation, which means that the operator is placed between the operand and the value.
For more information about the *Filter* parameter, type `Get-Help about_ActiveDirectory_Filter`.

Syntax:

The following syntax uses Backus-Naur form to show how to use the PowerShell Expression Language for this parameter.

\<filter\>  ::= "{" \<FilterComponentList\> "}"

\<FilterComponentList\> ::= \<FilterComponent\> | \<FilterComponent\> \<JoinOperator\> \<FilterComponent\> | \<NotOperator\>  \<FilterComponent\>

\<FilterComponent\> ::= \<attr\> \<FilterOperator\> \<value\> | "(" \<FilterComponent\> ")"

\<FilterOperator\> ::= "-eq" | "-le" | "-ge" | "-ne" | "-lt" | "-gt"| "-approx" | "-bor" | "-band" | "-recursivematch" | "-like" | "-notlike"

\<JoinOperator\> ::= "-and" | "-or"

\<NotOperator\> ::= "-not"

\<attr\> ::= \<PropertyName\> | \<LDAPDisplayName of the attribute\>

\<value\>::= \<compare this value with an \<attr\> by using the specified \<FilterOperator\>\>

For a list of supported types for \<value\>, type `Get-Help about_ActiveDirectory_ObjectModel`.

Note: PowerShell wildcards other than \*, such as ?, are not supported by the *Filter* syntax.

Note: To query using LDAP query strings, use the *LDAPFilter* parameter.

```yaml
Type: String
Parameter Sets: Filter
Aliases:

Required: True
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
- A security accounts manager account name (sAMAccountName)

The cmdlet searches the default naming context or partition to find the object.
If two or more objects are found, the cmdlet returns a non-terminating error.

This parameter can also get this object through the pipeline or you can set this parameter to an object instance.

```yaml
Type: ADGroup
Parameter Sets: Identity
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -LDAPFilter
Specifies an LDAP query string that is used to filter Active Directory objects.
You can use this parameter to run your existing LDAP queries.
The *Filter* parameter syntax supports the same functionality as the LDAP syntax.
For more information, see the *Filter* parameter description or type `Get-Help about_ActiveDirectory_Filter`.

```yaml
Type: String
Parameter Sets: LdapFilter
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
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
- If the target AD LDS instance has a default naming context, the default value of *Partition* will be set to the default naming context.
To specify a default naming context for an AD LDS environment, set the **msDS-defaultNamingContext** property of the Active Directory directory service agent object (**nTDSDSA**) for the AD LDS instance.
- If none of the previous cases apply, the *Partition* parameter does not take any default value.

```yaml
Type: String
Parameter Sets: Identity
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Properties
Specifies the properties of the output object to retrieve from the server.
Use this parameter to retrieve properties that are not included in the default set.

Specify properties for this parameter as a comma-separated list of names.
To display all of the attributes that are set on the object, specify * (asterisk).

To specify an individual extended property, use the name of the property.
For properties that are not default or extended properties, you must specify the LDAP display name of the attribute.

To retrieve properties and display them for an object, you can use the Get-* cmdlet associated with the object and pass the output to the **Get-Member** cmdlet.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: Property

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResultPageSize
Specifies the number of objects to include in one page for an AD DS query.

The default is 256 objects per page.

```yaml
Type: Int32
Parameter Sets: Filter, LdapFilter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResultSetSize
Specifies the maximum number of objects to return for an AD DS query.
If you want to receive all of the objects, set this parameter to $Null (null value).
You can use Ctrl+C to stop the query and return of objects.

The default is $Null.

```yaml
Type: Int32
Parameter Sets: Filter, LdapFilter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SearchBase
Specifies an Active Directory path to search under.

When you run a cmdlet from an Active Directory provider drive, the default value of this parameter is the current path of the drive.

When you run a cmdlet outside of an Active Directory provider drive against an AD DS target, the default value of this parameter is the default naming context of the target domain.

When you run a cmdlet outside of an Active Directory provider drive against an AD LDS target, the default value is the default naming context of the target LDS instance if one has been specified by setting the **msDS-defaultNamingContext** property of the Active Directory directory service agent object (**nTDSDSA**) for the AD LDS instance.
If no default naming context has been specified for the target AD LDS instance, then this parameter has no default value.

When the value of the *SearchBase* parameter is set to an empty string and you are connected to a GC port, all partitions are searched.
If the value of the *SearchBase* parameter is set to an empty string and you are not connected to a GC port, an error is thrown.

```yaml
Type: String
Parameter Sets: Filter, LdapFilter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SearchScope
Specifies the scope of an Active Directory search.
The acceptable values for this parameter are:

- Base or 0
- OneLevel or 1
- Subtree or 2

A Base query searches only the current path or object.
A OneLevel query searches the immediate children of that path or object.
A Subtree query searches the current path or object and all children of that path or object.

```yaml
Type: ADSearchScope
Parameter Sets: Filter, LdapFilter
Aliases:
Accepted values: Base, OneLevel, Subtree

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Server
Specifies the Active Directory Domain Services instance to connect to, by providing one of the following values for a corresponding domain name or directory server.
The service may be any of the following: Active Directory Lightweight Domain Services, Active Directory Domain Services or Active Directory Snapshot instance.

Specify the Active Directory Domain Services instance in one of the following ways:

Domain name values:

- Fully qualified domain name
- NetBIOS name

Directory server values:

- Fully qualified directory server name
- NetBIOS name
- Fully qualified directory server name and port

The default value for this parameter is determined by one of the following methods in the order that they are listed:

- By using the *Server* value from objects passed through the pipeline
- By using the server information associated with the Active Directory Domain Services Windows PowerShell provider drive, when the cmdlet runs in that drive
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

### -ShowMemberTimeToLive
Indicates that this cmdlet displays Time to Live (TTL) values for group members.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None or Microsoft.ActiveDirectory.Management.ADGroup
A group object is received by the *Identity* parameter.

## OUTPUTS

### Microsoft.ActiveDirectory.Management.ADGroup
Returns one or more group objects.

The **Get-ADGroup** cmdlet returns a default set of **ADGroup** property values.
To retrieve additional **ADGroup** properties, use the *Properties* parameter.

To view the properties for an **ADGroup** object, see the following examples.
To run these examples, replace \<group\> with a group identifier such as Administrators.

To get a list of the default set of properties of an **ADGroup** object, use the following command:

`Get-ADGroup`\<group\>`| Get-Member`

To get a list of all the properties of an **ADGroup** object, use the following command:

`Get-ADGroup`\<group\>`-Properties * | Get-Member`

## NOTES

## RELATED LINKS

[New-ADGroup](./New-ADGroup.md)

[Remove-ADGroup](./Remove-ADGroup.md)

[Set-ADGroup](./Set-ADGroup.md)

