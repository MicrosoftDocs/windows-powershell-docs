---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
Module Name: ActiveDirectory
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/activedirectory/get-adclaimtype?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ADClaimType
---

# Get-ADClaimType

## SYNOPSIS
Returns a claim type from Active Directory.

## SYNTAX

### Filter (Default)
```
Get-ADClaimType [-AuthType <ADAuthType>] [-Credential <PSCredential>] -Filter <String> [-Properties <String[]>]
 [-ResultPageSize <Int32>] [-ResultSetSize <Int32>] [-Server <String>] [<CommonParameters>]
```

### Identity
```
Get-ADClaimType [-AuthType <ADAuthType>] [-Credential <PSCredential>] [-Identity] <ADClaimType>
 [-Properties <String[]>] [-Server <String>] [<CommonParameters>]
```

### LdapFilter
```
Get-ADClaimType [-AuthType <ADAuthType>] [-Credential <PSCredential>] -LDAPFilter <String>
 [-Properties <String[]>] [-ResultPageSize <Int32>] [-ResultSetSize <Int32>] [-Server <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-ADClaimType** cmdlet returns a claim type defined in Active Directory.

## EXAMPLES

### Example 1: Get a list of all claim types using a filter
```
PS C:\> Get-ADClaimType -Filter *
```

This command retrieves a list of all claim types.

### Example 2: Get all the claim types that are sourced from the attribute title.
```
PS C:\> Get-ADClaimType -Filter "SourceAttribute -eq 'title'"
```

This command gets all the claim types that are sourced from the attribute title.

### Example 3: Get a claim type with a specified display name
```
PS C:\> Get-ADClaimType -Identity "Employee Type"
```

This command gets the claim type with display name Employee Type.

### Example 4: Get all properties of a claim type with a specified display name
```
PS C:\> Get-ADClaimType -Identity "Employee Type" -Properties *
```

This command gets all properties of the claim type with display name Employee Type.

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

The following syntax uses Backus-Naur form to show how to use the Windows PowerShell Expression Language for this parameter.

\<filter\>  ::= "{" \<FilterComponentList\> "}"

\<FilterComponentList\> ::= \<FilterComponent\> | \<FilterComponent\> \<JoinOperator\> \<FilterComponent\> | \<NotOperator\>  \<FilterComponent\>

\<FilterComponent\> ::= \<attr\> \<FilterOperator\> \<value\> | "(" \<FilterComponent\> ")"

\<FilterOperator\> ::= "-eq" | "-le" | "-ge" | "-ne" | "-lt" | "-gt"| "-approx" | "-bor" | "-band" | "-recursivematch" | "-like" | "-notlike"

\<JoinOperator\> ::= "-and" | "-or"

\<NotOperator\> ::= "-not"

\<attr\> ::= \<PropertyName\> | \<LDAPDisplayName of the attribute\>

\<value\>::= \<compare this value with an \<attr\> by using the specified \<FilterOperator\>\>

For a list of supported types for \<value\>, see about_ActiveDirectory_ObjectModel.

Note: PowerShell wildcards other than *, such as ?, are not supported by the *Filter* syntax.

Note: To query using Lightweight Directory Access Protocol (LDAP) query strings, use the *LDAPFilter* parameter.

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
The identifier in parentheses is the LDAP display name for the attribute.The acceptable values for this parameter are:

- A distinguished name
- A GUID (objectGUID)

This parameter can also get this object through the pipeline or you can set this parameter to an object instance.

```yaml
Type: ADClaimType
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
Specifies the number of objects to include in one page for an Active Directory Domain Services query.

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
Specifies the maximum number of objects to return for an Active Directory Domain Services query.
If you want to receive all of the objects, set this parameter to $Null (null value).
You can use Ctrl+C to stop the query and return of objects.

The default is $null.

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

### -Server
Specifies the Active Directory Domain Services instance to connect to, by providing one of the following values for a corresponding domain name or directory server.
The service may be any of the following:  Active Directory Lightweight Domain Services, Active Directory Domain Services or Active Directory snapshot instance.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None or Microsoft.ActiveDirectory.Management.ADClaimType

## OUTPUTS

### Microsoft.ActiveDirectory.Management.ADClaimType

## NOTES

## RELATED LINKS

[New-ADClaimType](./New-ADClaimType.md)

[Remove-ADClaimType](./Remove-ADClaimType.md)

[Set-ADClaimType](./Set-ADClaimType.md)

[AD DS Administration Cmdlets in Windows PowerShell](./activedirectory.md)

