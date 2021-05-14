---
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
Module Name: ActiveDirectory
ms.date: 10/30/2017
online version: https://docs.microsoft.com/powershell/module/activedirectory/get-adreplicationsite?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ADReplicationSite
---

# Get-ADReplicationSite

## SYNOPSIS
Returns a specific Active Directory replication site or a set of replication site objects based on a specified filter.

## SYNTAX

### Identity (Default)
```
Get-ADReplicationSite [-AuthType <ADAuthType>] [-Credential <PSCredential>] [[-Identity] <ADReplicationSite>]
 [-Properties <String[]>] [-Server <String>] [<CommonParameters>]
```

### Filter
```
Get-ADReplicationSite [-AuthType <ADAuthType>] [-Credential <PSCredential>] -Filter <String>
 [-Properties <String[]>] [-Server <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-ADReplicationSite** cmdlet returns a specific Active Directory replication site or a set of replication site objects based on a specified filter.
Sites are used in Active Directory to either enable clients to discover network resources (published shares, domain controllers) close to the physical location of a client computer or to reduce network traffic over wide area network (WAN) links.
Sites can also be used to optimize replication between domain controllers.

## EXAMPLES

### Example 1: Get all replication sites
```
PS C:\>Get-ADReplicationSite -Filter *
```

This command gets all Active Directory Replication sites.

### Example 2: Get replication sites by flag
```
PS C:\>Get-ADReplicationSite -Properties * -Filter "WindowsServer2003KCCSiteLinkBridgingEnabled -eq `$True"
```

This command gets all sites that have the WindowsServer2003KCCBehaviorEnabled flag turned on.
The **Properties** parameter must be set because the **WindowsServer2003KCCSiteLinkBridgingEnabled** property is not retrieved by default.

### Example 3: Get replication sites by name
```
PS C:\>Get-ADReplicationSite -Identity NorthAmerica
```

This command gets the site with name NorthAmerica.

### Example 4: Get replication sites by name and property
```
PS C:\>Get-ADReplicationSite -Identity NorthAmerica -Properties AutomaticInterSiteTopologyGenerationEnabled
```

This command gets the **AutomaticInterSiteTopologyGenerationEnabled** property of the site with name NorthAmerica.

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
Default value: Microsoft.ActiveDirectory.Management.AuthType.Negotiate
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
Specifies the user account credentials to use to perform this task.
The default credentials are the credentials of the currently logged on user unless the cmdlet is run from an Active Directory module for Windows PowerShell provider drive.
If the cmdlet is run from such a provider drive, the account associated with the drive is the default.

To specify this parameter, you can type a user name, such as User1 or Domain01\User01 or you can specify a **PSCredential** object.
If you specify a user name for this parameter, the cmdlet prompts for a password.

You can also create a **PSCredential** object by using a script or by using the Get-Credentialhttp://go.microsoft.com/fwlink/?LinkID=293936 cmdlet.
You can then set the **Credential** parameter to the **PSCredential** object.

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

Note: PowerShell wildcards other than *, such as ?, are not supported by the **Filter** syntax.

Note: To query using LDAP query strings, use the **LDAPFilter** parameter.

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

```yaml
Type: ADReplicationSite
Parameter Sets: Identity
Aliases: 

Required: False
Position: 0
Default value: All Sites (Filter *)
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Properties
Specifies the properties of the output object to retrieve from the server.
Use this parameter to retrieve properties that are not included in the default set.

Specify properties for this parameter as a comma-separated list of names.
To display all of the attributes that are set on the object, specify * (asterisk).

To specify an individual extended property, use the name of the property.
For properties that are not default or extended properties, you must specify the LDAP display name of the attribute.

To retrieve properties and display them for an object, you can use the Get-* cmdlet associated with the object and pass the output to the Get-Memberhttp://go.microsoft.com/fwlink/?LinkID=113322 cmdlet.

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
Specifies the Active Directory Domain Services (AD DS) instance to connect to, by providing one of the following values for a corresponding domain name or directory server.
The service may be any of the following: Active Directory Lightweight Directory Services (AD LDS), AD DS, or Active Directory snapshot instance.

Specify the AD DS instance in one of the following ways:  

 Domain name values:

- Fully qualified domain name
- NetBIOS name

Directory server values:  

- Fully qualified directory server name
- NetBIOS name
- Fully qualified directory server name and port

The default value for this parameter is determined by one of the following methods in the order that they are listed:

- By using the **Server** value from objects passed through the pipeline
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None or Microsoft.ActiveDirectory.Management.ADReplicationSite
A site object is received by the **Identity** parameter.

## OUTPUTS

### Microsoft.ActiveDirectory.Management.ADReplicationSite

## NOTES

## RELATED LINKS

[New-ADReplicationSite](./New-ADReplicationSite.md)

[Remove-ADReplicationSite](./Remove-ADReplicationSite.md)

[Set-ADReplicationSite](./Set-ADReplicationSite.md)

