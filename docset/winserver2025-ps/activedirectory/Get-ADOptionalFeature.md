---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
Module Name: ActiveDirectory
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/activedirectory/get-adoptionalfeature?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ADOptionalFeature
---

# Get-ADOptionalFeature

## SYNOPSIS
Gets one or more Active Directory optional features.

## SYNTAX

### Filter (Default)
```
Get-ADOptionalFeature [-AuthType <ADAuthType>] [-Credential <PSCredential>] -Filter <String>
 [-Properties <String[]>] [-ResultPageSize <Int32>] [-ResultSetSize <Int32>] [-SearchBase <String>]
 [-SearchScope <ADSearchScope>] [-Server <String>] [<CommonParameters>]
```

### Identity
```
Get-ADOptionalFeature [-AuthType <ADAuthType>] [-Credential <PSCredential>] [-Identity] <ADOptionalFeature>
 [-Properties <String[]>] [-Server <String>] [<CommonParameters>]
```

### LdapFilter
```
Get-ADOptionalFeature [-AuthType <ADAuthType>] [-Credential <PSCredential>] -LDAPFilter <String>
 [-Properties <String[]>] [-ResultPageSize <Int32>] [-ResultSetSize <Int32>] [-SearchBase <String>]
 [-SearchScope <ADSearchScope>] [-Server <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-ADOptionalFeature** cmdlet gets an optional feature or performs a search to retrieve multiple optional features from an Active Directory.

The *Identity* parameter specifies the Active Directory optional feature that you want to get.
You can identify an optional feature by its distinguished name, feature GUID, or object GUID.
You can also set the parameter to an optional feature object variable, such as `$<localOptionalFeatureObject>` or you can pass an optional feature object through the pipeline to the *Identity* parameter.

To search for and retrieve more than one optional feature, use the *Filter* or *LDAPFilter* parameters.
The *Filter* parameter uses the PowerShell Expression Language to write query strings for Active Directory.
PowerShell Expression Language syntax provides rich type conversion support for value types received by the *Filter* parameter.
For more information about the *Filter* parameter syntax, type `Get-Help about_ActiveDirectory_Filter`.
If you have existing Lightweight Directory Access Protocol (LDAP) query strings, you can use the *LDAPFilter* parameter.

This cmdlet gets a default set of optional feature object properties.
To get additional properties use the *Properties* parameter.
For more information about the how to determine the properties for computer objects, see the *Properties* parameter description.

## EXAMPLES

### Example 1: Get all available features in a forest
```
PS C:\> Get-ADOptionalFeature -Filter *
```

This command gets all of the available optional features in the current forest.

### Example 2: Get a specified optional feature
```
PS C:\> Get-ADOptionalFeature -Identity 'Recycle Bin Feature'
```

This command gets the optional feature with the name Recycle Bin Feature.

### Example 3: Get a feature by its GUID
```
PS C:\> Get-ADOptionalFeature -Identity 766ddcd8-acd0-445e-f3b9-a7f9b6744f2a
```

This command gets the optional feature with the feature GUID 766ddcd8-acd0-445e-f3b9-a7f9b6744f2a.

### Example 4: Get a specified feature in an AD LDS instance
```
PS C:\> Get-ADOptionalFeature -Identity 'Recycle Bin Feature' -Server server1:50000
```

This command gets the optional feature Recycle Bin Feature in an AD LDS instance.

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

Note: PowerShell wildcards other than asterisk (*), such as question mark (?), are not supported by the *Filter* syntax.

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
Specifies an Active Directory optional feature object by providing one of the following values.
The identifier in parentheses is the LDAP display name for the attribute.
The acceptable values for this parameter are:

- A fully qualified domain name
- A GUID (objectGUID)

The cmdlet searches the default naming context or partition to find the object.
If two or more objects are found, the cmdlet returns a non-terminating error.

This parameter can also get this object through the pipeline or you can set this parameter to an optional feature object instance.

```yaml
Type: ADOptionalFeature
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
Specifies the number of objects to include in one page for an Active Directory Domain Services (AD DS) query.

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
Specifies the Active Directory Domain Services (AD DS) instance to connect to, by providing one of the following values for a corresponding domain name or directory server.
The service may be any of the following: Active Directory Lightweight Domain Services (AD LDS), AD DS, or Active Directory snapshot instance.

Specify the AD DS instance in one of the following ways:

Domain name values:

- FQDN
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

### None or Microsoft.ActiveDirectory.Management.ADOptionalFeature
An optional feature object is received by the *Identity* parameter.

## OUTPUTS

### Microsoft.ActiveDirectory.Management.ADOptionalFeature
Returns one or more optional feature objects.

This cmdlet returns a default set of **ADOptionalFeature** property values.
To retrieve additional **ADOptionalFeature** properties, use the *Properties* parameter.

To view the properties for an **ADOptionalFeature** object, see the following examples.
To run these examples, replace \<optional feature\> with an optional feature identifier, such as distinguished name of the optional feature.

To get a list of the default set of properties of an **ADOptionalFeature** object, use the following command:

`Get-ADOptionalFeature`\<optional feature\>`| Get-Member`

To get a list of all the properties of an **ADOptionalFeature** object, use the following command:

`Get-ADOptionalFeature`\<optional feature\>`-Properties ALL | Get-Member`

## NOTES

## RELATED LINKS

[Disable-ADOptionalFeature](./Disable-ADOptionalFeature.md)

[Enable-ADOptionalFeature](./Enable-ADOptionalFeature.md)

