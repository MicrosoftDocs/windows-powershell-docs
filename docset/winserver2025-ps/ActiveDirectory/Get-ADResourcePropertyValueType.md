---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
Module Name: ActiveDirectory
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/activedirectory/get-adresourcepropertyvaluetype?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ADResourcePropertyValueType
---

# Get-ADResourcePropertyValueType

## SYNOPSIS
Gets a resource property value type from Active Directory.

## SYNTAX

### Filter (Default)
```
Get-ADResourcePropertyValueType [-AuthType <ADAuthType>] [-Credential <PSCredential>] -Filter <String>
 [-Properties <String[]>] [-Server <String>] [<CommonParameters>]
```

### Identity
```
Get-ADResourcePropertyValueType [-AuthType <ADAuthType>] [-Credential <PSCredential>]
 [-Identity] <ADResourcePropertyValueType> [-Properties <String[]>] [-Server <String>] [<CommonParameters>]
```

### LdapFilter
```
Get-ADResourcePropertyValueType [-AuthType <ADAuthType>] [-Credential <PSCredential>] -LDAPFilter <String>
 [-Properties <String[]>] [-Server <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-ADResourcePropertyValueType** cmdlet retrieves a resource property value type from Active Directory.
The resource property value type supports the following Active Directory primitives (**ValueType**, **IsSingleValued**, **RestrictValues**) and a Boolean indicating whether **SuggestedValues** are allowed.

## EXAMPLES

### Example 1: Get all resource property value types
```
PS C:\> Get-ADResourcePropertyValueType -Filter * | Format-Table Name
```

This command gets the names of all resource property value types.

### Example 2: Get resource property value types for specified resource properties
```
PS C:\> Get-ADResourcePropertyValueType -Filter "ResourceProperties -eq 'Country' -or ResourceProperties -eq 'Authors'"
```

This command gets all resource property value types that the resource properties Country and Authors use.

### Example 3: Get the specified resource property value type
```
PS C:\> Get-ADResourcePropertyValueType -Identity "MS-DS-Text"
```

This command gets a resource property value type named MS-DS-Text.

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
Specifies an Active Directory user object by providing one of the following property values.
The identifier in parentheses is the Lightweight Directory Access Protocol (LDAP) display name for the attribute.
The acceptable values for this parameter are:

- A distinguished name
- A GUID (objectGUID)
- A security identifier (objectSid)
- A SAM account name (sAMAccountName)

This parameter can also get this object through the pipeline or you can set this parameter to an object instance.

```yaml
Type: ADResourcePropertyValueType
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
For more information, type `Get-Help Get-Member`.

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

### -Server
Specifies the Active Directory Domain Services instance to connect to, by providing one of the following values for a corresponding domain name or directory server.
The service may be any of the following:  Active Directory Lightweight Domain Services, Active Directory Domain Services or Active Directory Snapshot instance.

Domain name values:

- Fully qualified domain name (FQDN)
- NetBIOS name

Directory server values:

- Fully qualified domain name (FQDN)
- NetBIOS name

The default value for the *Server* parameter is determined by one of the following methods in the order that they are listed:

- By using *Server* value from objects passed through the pipeline.
- By using the server information associated with the Active Directory PowerShell provider drive, when running under that drive.
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None or Microsoft.ActiveDirectory.Management.ADResourcePropertyValueType

## OUTPUTS

### Microsoft.ActiveDirectory.Management.ADResourcePropertyValueType
- Default
- 1 ValueType
- 2 IsSingleValued
- 3 RestrictValues
- 4 AreSuggestedValuesPresent

## NOTES

## RELATED LINKS

