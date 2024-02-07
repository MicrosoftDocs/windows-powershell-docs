---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
Module Name: ActiveDirectory
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/activedirectory/get-adserviceaccount?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ADServiceAccount
---

# Get-ADServiceAccount

## SYNOPSIS
Gets one or more Active Directory managed service accounts or group managed service accounts.

## SYNTAX

### Filter (Default)
```
Get-ADServiceAccount [-AuthType <ADAuthType>] [-Credential <PSCredential>] -Filter <String>
 [-Properties <String[]>] [-ResultPageSize <Int32>] [-ResultSetSize <Int32>] [-SearchBase <String>]
 [-SearchScope <ADSearchScope>] [-Server <String>] [<CommonParameters>]
```

### Identity
```
Get-ADServiceAccount [-AuthType <ADAuthType>] [-Credential <PSCredential>] [-Identity] <ADServiceAccount>
 [-Partition <String>] [-Properties <String[]>] [-Server <String>] [<CommonParameters>]
```

### LdapFilter
```
Get-ADServiceAccount [-AuthType <ADAuthType>] [-Credential <PSCredential>] -LDAPFilter <String>
 [-Properties <String[]>] [-ResultPageSize <Int32>] [-ResultSetSize <Int32>] [-SearchBase <String>]
 [-SearchScope <ADSearchScope>] [-Server <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-ADServiceAccount** cmdlet gets a managed service account or performs a search to get managed service accounts.

The **Identity** parameter specifies the Active Directory managed service account to get.
You can identify a managed service account by its distinguished name, GUID, security identifier (SID), or Security Account Manager (SAM) account name.
You can also set the parameter to a managed service account object variable, such as `$<localServiceAccountObject>` or pass a managed service account object through the pipeline to the **Identity** parameter.

To search for and retrieve more than one managed service account, use the **Filter** or **LDAPFilter** parameters.
The **Filter** parameter uses the PowerShell Expression Language to write query strings for Active Directory.
PowerShell Expression Language syntax provides rich type conversion support for value types received by the **Filter** parameter.
For more information about the **Filter** parameter syntax, type `Get-Help about_ActiveDirectory_Filter`.
If you have existing Lightweight Directory Access Protocol (LDAP) query strings, you can use the **LDAPFilter** parameter.

This cmdlet gets a default set of managed service account object properties.
To get additional properties use the **Properties** parameter.
For more information about the how to determine the properties for service account objects, see the **Properties** parameter description.

## EXAMPLES

### Example 1: Get a managed service account by its Security Account Manager name
```powershell
PS C:\> Get-ADServiceAccount -Identity service1
```
```output
Enabled           : True
Name              : service1
UserPrincipalName :
SamAccountName    : service1$
ObjectClass       : msDS-ManagedServiceAccount
SID               : S-1-5-21-159507390-2980359153-3438059098-29770
ObjectGUID        : eaa435ee-6ebc-44dd-b4b6-dc1bb5bcd23a
HostComputers     :
DistinguishedName : CN=service1,CN=Managed Service Accounts,DC=contoso,DC=com
```

This command gets a managed service account with SAM account name service1.

### Example 2: Get a managed service account by its SID
```powershell
PS C:\> Get-ADServiceAccount -Identity S-1-5-21-159507390-2980359153-3438059098-29770
```
```output
Enabled           : True
Name              : service1
UserPrincipalName :
SamAccountName    : service1$
ObjectClass       : msDS-ManagedServiceAccount
SID               : S-1-5-21-159507390-2980359153-3438059098-29770
ObjectGUID        : eaa435ee-6ebc-44dd-b4b6-dc1bb5bcd23a
HostComputers     :
DistinguishedName : CN=service1,CN=Managed Service Accounts,DC=contoso,DC=com
```

This command gets the managed service account with SID `S-1-5-21-159507390-2980359153-3438059098-29770`.

### Example 3: Get a filtered list of managed service accounts
```powershell
PS C:\> Get-ADServiceAccount -Filter "HostComputers -eq 'CN=SQL-Server-1, DC=contoso,DC=com'"
```
```output
Enabled           : True
Name              : service1
UserPrincipalName :
SamAccountName    : service1$
ObjectClass       : msDS-ManagedServiceAccount
SID               : S-1-5-21-159507390-2980359153-3438059098-29770
ObjectGUID        : eaa435ee-6ebc-44dd-b4b6-dc1bb5bcd23a
HostComputers     : {CN=SQL-Server-1, DC=contoso,DC=com}
DistinguishedName : CN=service1,CN=Managed Service Accounts,DC=contoso,DC=com
```

This command gets the managed service accounts allowed to be used on the computer `CN=SQL-Server-1,DC=contoso,DC=com`.

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

To specify this parameter, you can type a user name, such as `User1` or `Domain01\User01` or you can specify a **PSCredential** object.
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
The PowerShell Expression Language syntax provides rich type-conversion support for value types received by the **Filter** parameter.
The syntax uses an in-order representation, which means that the operator is placed between the operand and the value.
For more information about the **Filter** parameter, type `Get-Help about_ActiveDirectory_Filter`.

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
Specifies an Active Directory account object by providing one of the following property values.
The identifier in parentheses is the LDAP display name for the attribute.
The acceptable values for this parameter are:

- A distinguished name
- A GUID (objectGUID)
- A security identifier (objectSid)
- A SAM account name (sAMAccountName)

The cmdlet searches the default naming context or partition to find the object.
If two or more objects are found, the cmdlet returns a non-terminating error.

This parameter can also get this object through the pipeline or you can set this parameter to an object instance.

```yaml
Type: ADServiceAccount
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
The **Filter** parameter syntax supports the same functionality as the LDAP syntax.
For more information, see the **Filter** parameter description or type `Get-Help about_ActiveDirectory_Filter`.

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
The cmdlet searches this partition to find the object defined by the **Identity** parameter.

In many cases, a default value will be used for the **Partition** parameter if no value is specified.
The rules for determining the default value are given below.
Note that rules listed first are evaluated first and once a default value can be determined, no further rules will be evaluated.

In AD DS environments, a default value for **Partition** will be set in the following cases:

- If the **Identity** parameter is set to a distinguished name, the default value of **Partition** is automatically generated from this distinguished name.
- If running cmdlets from an Active Directory provider drive, the default value of **Partition** is automatically generated from the current path in the drive.
- If none of the previous cases apply, the default value of **Partition** will be set to the default partition or naming context of the target domain.

In AD LDS environments, a default value for Partition will be set in the following cases:

- If the **Identity** parameter is set to a distinguished name, the default value of **Partition** is automatically generated from this distinguished name.
- If running cmdlets from an Active Directory provider drive, the default value of **Partition** is automatically generated from the current path in the drive.
- If the target AD LDS instance has a default naming context, the default value of **Partition** will be set to the default naming context.
To specify a default naming context for an AD LDS environment, set the **msDS-defaultNamingContext** property of the Active Directory directory service agent (DSA) object (**nTDSDSA**) for the AD LDS instance.
- If none of the previous cases apply, the **Partition** parameter will not take any default value.

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
If you want to receive all of the objects, set this parameter to `$Null` (null value).
You can use Ctrl+C to stop the query and return of objects.

The default is `$Null`.

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

When you run a cmdlet outside of an Active Directory provider drive against an AD LDS target, the default value is the default naming context of the target LDS instance if one has been specified by setting the **msDS-defaultNamingContext** property of the Active Directory directory service agent (DSA) object (**nTDSDSA**) for the AD LDS instance.
If no default naming context has been specified for the target AD LDS instance, then this parameter has no default value.

When the value of the **SearchBase** parameter is set to an empty string and you are connected to a GC port, all partitions will be searched.
If the value of the **SearchBase** parameter is set to an empty string and you are not connected to a GC port, an error will be thrown.

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

Domain name values:

- Fully qualified domain name (FQDN)
- NetBIOS name

Directory server values:

- Fully qualified directory server name
- NetBIOS name
- Fully qualified directory server name and port

The default value for the **Server** parameter is determined by one of the following methods in the order that they are listed:

- By using **Server** value from objects passed through the pipeline.
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
This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None or Microsoft.ActiveDirectory.Management.ADServiceAccount
A managed service account object is received by the **Identity** parameter.

## OUTPUTS

### Microsoft.ActiveDirectory.Management.ADServiceAccount
Returns one or more managed service account (MSA) objects.

This cmdlet returns a default set of ADService account property values.
To retrieve additional ADService account properties, use the **Properties** parameter.

## NOTES
* This cmdlet does not work with AD LDS.

## RELATED LINKS

[Install-ADServiceAccount](./Install-ADServiceAccount.md)

[New-ADServiceAccount](./New-ADServiceAccount.md)

[Remove-ADServiceAccount](./Remove-ADServiceAccount.md)

[Set-ADServiceAccount](./Set-ADServiceAccount.md)

[Uninstall-ADServiceAccount](./Uninstall-ADServiceAccount.md)

