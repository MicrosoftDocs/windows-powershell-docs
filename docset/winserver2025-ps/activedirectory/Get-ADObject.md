---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
Module Name: ActiveDirectory
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/activedirectory/get-adobject?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ADObject
---

# Get-ADObject

## SYNOPSIS
Gets one or more Active Directory objects.

## SYNTAX

### Filter (Default)
```
Get-ADObject [-AuthType <ADAuthType>] [-Credential <PSCredential>] -Filter <String> [-IncludeDeletedObjects]
 [-Properties <String[]>] [-ResultPageSize <Int32>] [-ResultSetSize <Int32>] [-SearchBase <String>]
 [-SearchScope <ADSearchScope>] [-Server <String>] [<CommonParameters>]
```

### Identity
```
Get-ADObject [-AuthType <ADAuthType>] [-Credential <PSCredential>] [-Identity] <ADObject>
 [-IncludeDeletedObjects] [-Partition <String>] [-Properties <String[]>] [-Server <String>]
 [<CommonParameters>]
```

### LdapFilter
```
Get-ADObject [-AuthType <ADAuthType>] [-Credential <PSCredential>] [-IncludeDeletedObjects]
 -LDAPFilter <String> [-Properties <String[]>] [-ResultPageSize <Int32>] [-ResultSetSize <Int32>]
 [-SearchBase <String>] [-SearchScope <ADSearchScope>] [-Server <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-ADObject** cmdlet gets an Active Directory object or performs a search to get multiple objects.

The *Identity* parameter specifies the Active Directory object to get.
You can identify the object to get by its distinguished name or GUID.
You can also set the parameter to an Active Directory object variable, such as `$<localADObject>` or pass an object through the pipeline to the *Identity* parameter.

To search for and get more than one object, use the *Filter* or *LDAPFilter* parameters.
The *Filter* parameter uses the PowerShell Expression Language to write query strings for Active Directory.
PowerShell Expression Language syntax provides rich type conversion support for value types received by the *Filter* parameter.
For more information about the *Filter* parameter syntax, type `Get-Help about_ActiveDirectory_Filter`.
If you have existing Lightweight Directory Access Protocol (LDAP) query strings, you can use the *LDAPFilter* parameter.

This cmdlet gets a default set of Active Directory object properties.
To get additional properties use the *Properties* parameter.
For more information about the how to determine the properties for computer objects, see the *Properties* parameter description.

## EXAMPLES

### Example 1: Get the sites for a domain using LDAP filter syntax
```
PS C:\> Get-ADObject -LDAPFilter "(objectClass=site)" -SearchBase 'CN=Configuration,DC=Fabrikam,DC=Com' -Properties CanonicalName | FT Name,CanonicalName -A
Name CanonicalName
---- -------------
HQ   FABRIKAM.COM/Configuration/Sites/HQ
BO1  FABRIKAM.COM/Configuration/Sites/BO1
BO2  FABRIKAM.COM/Configuration/Sites/BO2
BO3  FABRIKAM.COM/Configuration/Sites/BO3
```

This command displays a list of sites for Fabrikam using the LDAP filter syntax.

### Example 2: Get the sites from the configuration naming context
```
PS C:\> Get-ADObject -Filter 'ObjectClass -eq "site"' -SearchBase 'CN=Configuration,DC=Fabrikam,DC=Com' -Properties siteObjectBL | foreach {$_.siteObjectBL}
CN=192.167.1.0/26,CN=Subnets,CN=Sites,CN=Configuration,DC=FABRIKAM,DC=COM
CN=192.166.1.0/26,CN=Subnets,CN=Sites,CN=Configuration,DC=FABRIKAM,DC=COM
CN=192.168.1.0/26,CN=Subnets,CN=Sites,CN=Configuration,DC=FABRIKAM,DC=COM
CN=192.165.1.0/26,CN=Subnets,CN=Sites,CN=Configuration,DC=FABRIKAM,DC=COM
CN=192.164.1.0/26,CN=Subnets,CN=Sites,CN=Configuration,DC=FABRIKAM,DC=COM
CN=192.163.1.0/26,CN=Subnets,CN=Sites,CN=Configuration,DC=FABRIKAM,DC=COM
CN=192.162.1.0/26,CN=Subnets,CN=Sites,CN=Configuration,DC=FABRIKAM,DC=COM
CN=192.161.1.0/26,CN=Subnets,CN=Sites,CN=Configuration,DC=FABRIKAM,DC=COM
CN=192.160.1.0/26,CN=Subnets,CN=Sites,CN=Configuration,DC=FABRIKAM,DC=COM
CN=192.159.1.0/26,CN=Subnets,CN=Sites,CN=Configuration,DC=FABRIKAM,DC=COM
CN=192.158.1.0/26,CN=Subnets,CN=Sites,CN=Configuration,DC=FABRIKAM,DC=COM
CN=192.157.1.0/26,CN=Subnets,CN=Sites,CN=Configuration,DC=FABRIKAM,DC=COM
```

This command gets the **Site** objects from the configuration naming context and displays a list of **siteObjectBL** properties.

### Example 3: Get all objects with a specified attribute
```
PS C:\> $ChangeDate = New-Object DateTime(2008, 11, 18, 1, 40, 02)
PS C:\> Get-ADObject -Filter 'whenChanged -gt $ChangeDate' -IncludeDeletedObjects
```

This command gets all the objects, including the deleted ones, whose **whenChanged** attribute is greater than the specified date.
Note that both deleted and non-deleted (and non-recycled) objects matching the filter are returned.

### Example 4: Get deleted objects with a specified attribute
```
PS C:\> $ChangeDate = New-Object DateTime(2008, 11, 18, 1, 40, 02)
PS C:\> Get-ADObject -Filter 'whenChanged -gt $ChangeDate -and isDeleted -eq $True -and -not (isRecycled -eq $True) -and name -ne "Deleted Objects"' -IncludeDeletedObjects


ObjectGUID        : 98118958-91c7-437d-8ada-ba0b66db823b
Deleted           : True
DistinguishedName : CN=Andrew Ma\0ADEL:98118958-91c7-437d-8ada-ba0b66db823b,CN=Deleted Objects,DC=FABRIKAM,DC=COM
Name              : Andrew Ma
DEL:98118958-91c7-437d-8ada-ba0b66db823b
ObjectClass       : user
```

This example gets all the deleted objects, whose **whenChanged** attribute is greater than the specified date.
The clause `name -ne "Deleted Objects"` ensures that the Deleted Objects Container is not returned.
This example only returns objects that can be restored.

### Example 5: Get specified objects that were deleted after a specified date
```
PS C:\> $ChangeDate = New-Object DateTime(2008, 11, 18, 1, 40, 02)
PS C:\> Get-ADObject -Filter 'whenChanged -gt $ChangeDate -and isDeleted -eq $True -and -not (isRecycled -eq $True) -and lastKnownParent -eq "OU=Accounting,DC=Fabrikam,DC=com"' -IncludeDeletedObjects


ObjectGUID        : 12d53e7f-aaf7-4790-b41a-da19044504db
Deleted           : True
DistinguishedName : CN=Craig Dewar\0ADEL:12d53e7f-aaf7-4790-b41a-da19044504db,CN=Deleted Objects,DC=Fabrikam,DC=com
Name              : Craig Dewar
DEL:12d53e7f-aaf7-4790-b41a-da19044504db
ObjectClass       : user
```

This example gets all the deleted objects whose **whenChanged** attribute is greater than the specified date and at the time of deletion were the children of the specified organizational unit.

### Example 6: Get information for a specified object of an LDS instance
```
PS C:\> Get-ADObject -Identity "DC=AppNC" -Server "FABRIKAM-SRV1:60000"
ObjectGUID                    DistinguishedName             Name                          ObjectClass
----------                    -----------------             ----                          -----------
62b2e185-9322-4980-9c93-cf... DC=AppNC                      AppNC                         domainDNS
```

This command gets the information of the **domainDNS** object of an LDS instance.

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

Note: PowerShell wildcards other than *, such as ?, are not supported by the *Filter* syntax.

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
Specifies an Active Directory object by providing one of the following property values.
The identifier in parentheses is the LDAP display name for the attribute.
The acceptable values for this parameter are:

- A distinguished name
- A GUID (objectGUID)

The cmdlet searches the default naming context or partition to find the object.
If two or more objects are found, the cmdlet returns a non-terminating error.

This parameter can also get this object through the pipeline or you can set this parameter to an object instance.

Derived types, such as the following, are also accepted:

- **Microsoft.ActiveDirectory.Management.ADGroup**
- **Microsoft.ActiveDirectory.Management.ADUser**
- **Microsoft.ActiveDirectory.Management.ADComputer**
- **Microsoft.ActiveDirectory.Management.ADServiceAccount**
- **Microsoft.ActiveDirectory.Management.ADFineGrainedPasswordPolicy**
- **Microsoft.ActiveDirectory.Management.ADDomain**

```yaml
Type: ADObject
Parameter Sets: Identity
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -IncludeDeletedObjects
Indicates that this cmdlet retrieves deleted objects and the deactivated forward and backward links.
When this parameter is specified, the cmdlet uses the following LDAP controls:

- Show Deleted Objects (1.2.840.113556.1.4.417)
- Show Deactivated Links (1.2.840.113556.1.4.2065)

Note: If this parameter is not specified, the cmdlet does not return or operate on deleted objects.

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
- If the target AD LDS instance has a default naming context, the default value of *Partition* is set to the default naming context.
To specify a default naming context for an AD LDS environment, set the **msDS-defaultNamingContext** property of the Active Directory directory service agent object (**nTDSDSA**) for the AD LDS instance.
- If none of the previous cases apply, the *Partition* parameter does not take a default value.

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
Specifies an Active Directory path to search.

When you run a cmdlet from an Active Directory provider drive, the default value of this parameter is the current path of the drive.

When you run a cmdlet outside of an Active Directory provider drive against an AD DS target, the default value of this parameter is the default naming context of the target domain.

When you run a cmdlet outside of an Active Directory provider drive against an AD LDS target, the default value is the default naming context of the target AD LDS instance if one has been specified by setting the **msDS-defaultNamingContext** property of the Active Directory directory service agent object (**nTDSDSA**) for the AD LDS instance.
If no default naming context has been specified for the target AD LDS instance, then this parameter has no default value.

When the value of the *SearchBase* parameter is set to an empty string and you are connected to a global catalog (GC) port, all partitions are searched.
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

### None or Microsoft.ActiveDirectory.Management.ADObject
An Active Directory object is received by the *Identity* parameter.
Derived types, such as the following, are also accepted:

- **Microsoft.ActiveDirectory.Management.ADGroup**
- **Microsoft.ActiveDirectory.Management.ADUser**
- **Microsoft.ActiveDirectory.Management.ADComputer**
- **Microsoft.ActiveDirectory.Management.ADServiceAccount**
- **Microsoft.ActiveDirectory.Management.ADOrganizationalUnit**
- **Microsoft.ActiveDirectory.Management.ADFineGrainedPasswordPolicy**
- **Microsoft.ActiveDirectory.Management.ADDomain**

## OUTPUTS

### Microsoft.ActiveDirectory.Management.ADObject
Returns one or more Active Directory objects.

The **Get-ADObject** cmdlet returns a default set of ADObject property values.
To retrieve additional **ADObject** properties, use the *Properties* parameter of the cmdlet.

To view the properties for an **ADObject** object, see the following examples.
To run these examples, replace \<object\> with an Active Directory object identifier.

To get a list of the default set of properties of an ADObject object, use the following command:

`Get-ADObject`\<object\>`| Get-Member`

To get a list of all the properties of an **ADObject** object, use the following command:

`Get-ADObject`\<object\>`-Properties ALL | Get-Member`

## NOTES

## RELATED LINKS

[Move-ADObject](./Move-ADObject.md)

[New-ADObject](./New-ADObject.md)

[Remove-ADObject](./Remove-ADObject.md)

[Rename-ADObject](./Rename-ADObject.md)

[Restore-ADObject](./Restore-ADObject.md)

[Set-ADObject](./Set-ADObject.md)

[Sync-ADObject](./Sync-ADObject.md)

