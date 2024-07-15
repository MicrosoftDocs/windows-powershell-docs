---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
Module Name: ActiveDirectory
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/activedirectory/get-addomaincontroller?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ADDomainController
---

# Get-ADDomainController

## SYNOPSIS
Gets one or more Active Directory domain controllers based on discoverable services criteria, search parameters or by providing a domain controller identifier, such as the NetBIOS name.

## SYNTAX

### Identity (Default)
```
Get-ADDomainController [-AuthType <ADAuthType>] [-Credential <PSCredential>] [[-Identity] <ADDomainController>]
 [-Server <String>] [<CommonParameters>]
```

### DiscoverByService
```
Get-ADDomainController [-AuthType <ADAuthType>] [-AvoidSelf] [-Discover] [-DomainName <String>]
 [-ForceDiscover] [-MinimumDirectoryServiceVersion <ADMinimumDirectoryServiceVersion>] [-NextClosestSite]
 [-Service <ADDiscoverableService[]>] [-SiteName <String>] [-Writable] [<CommonParameters>]
```

### Filter
```
Get-ADDomainController [-AuthType <ADAuthType>] [-Credential <PSCredential>] -Filter <String>
 [-Server <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-ADDomainController** cmdlet gets the domain controllers specified by the parameters.
You can get domain controllers by setting the *Identity*, *Filter* or *Discover* parameters.

The *Identity* parameter specifies the domain controller to get.
You can identify a domain controller by its GUID, IPV4Address, global IPV6Address, or DNS host name.
You can also identify a domain controller by the name of the server object that represents the domain controller, the distinguished name of the NTDS settings object or the server object, the GUID of the NTDS settings object or the server object under the configuration partition, or the distinguished name of the computer object that represents the domain controller.
You can also set the *Identity* parameter to a domain controller object variable, such as `$<localDomainControllerObject>`, or pass a domain controller object through the pipeline to the *Identity* parameter.

To search for and retrieve more than one domain controller, use the *Filter* parameter.
The *Filter* parameter uses the Windows PowerShell Expression Language to write query strings for Active Directory.
Windows PowerShell Expression Language syntax provides rich type conversion support for value types received by the *Filter* parameter.
For more information about the *Filter* parameter syntax, type `Get-Help about_ActiveDirectory_Filter`.
You cannot use a Lightweight Directory Access Protocol (LDAP) query string with this cmdlet.

To get a domain controller by using the discovery mechanism of DCLocator, use the *Discover* parameter.
You can provide search criteria by setting parameters such as *Service*, *SiteName*, *DomainName*, *NextClosestSite*, *AvoidSelf*, and *ForceDiscover*.

## EXAMPLES

### Example 1: Get a domain controller in a specified site
```
PS C:\> Get-ADDomainController -Discover -Site "Default-First-Site-Name"
```

This command gets one available domain controller in the site specified by the *Site* parameter.
The command uses Discovery.

### Example 2: Get an available domain controller using force discovery in a specified site
```
PS C:\> Get-ADDomainController -Discover -Site "Default-First-Site-Name" -ForceDiscover
```

This command force discovers or finds one available domain controller in the site specified by the *Site* parameter.

### Example 3: Get a global catalog in the current forest using discovery
```
PS C:\> Get-ADDomainController -Discover -Service "GlobalCatalog"
```

This command gets a global catalog in the current forest using Discovery.

### Example 4: Get an available domain controller in the current domain using discovery
```
PS C:\> Get-ADDomainController -Discover
```

This command gets one available domain controller in the current domain using Discovery.

### Example 5: Get an available domain controller in a given domain using discovery
```
PS C:\> Get-ADDomainController -Discover -Domain "user01.com"
```

This command gets one available domain controller in a given domain using Discovery.

### Example 6: Get the primary domain controller that is advertising as a time server using discovery
```
PS C:\> Get-ADDomainController -Discover -Domain "corp.contoso.com" -Service "PrimaryDC","TimeService"
```

This command gets the primary domain controller using Discovery and make sure that is advertising as a time server.

### Example 7: Get a domain controller using its NetBIOS name
```
PS C:\> Get-ADDomainController -Identity "PDC-01"
```

This command gets a domain controller using its NetBIOS name.

### Example 8: Get a domain controller using its DNS host name in a specified site using administrator credentials
```
PS C:\> Get-ADDomainController -Identity "TK5-CORP-DC-10.user01.com" -Server "user01.com" -Credential "corp\administrator"
```

This command gets a domain controller using its DNS host name, in the domain specified by the *Site* parameter, specified in *Server* parameter, and specifying administrator credentials.

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

### -AvoidSelf
Specifies to not return the current computer as a domain controller.
If the current computer is not a domain controller, this parameter is ignored.
You can specify this parameter when you want to get the name of another domain controller in the domain.

```yaml
Type: SwitchParameter
Parameter Sets: DiscoverByService
Aliases:

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
Parameter Sets: Identity, Filter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Discover
Specifies to return a discoverable domain controller that meets the conditions specified by the cmdlet parameters.

To get a domain controller by using the discovery mechanism of DCLocator, use the *Discover* parameter.
Along with this parameter, you can provide search criteria by setting parameters such as *Service*, *SiteName*, *DomainName*, *NextClosestSite*, *AvoidSelf*, and *ForceDiscover*.

```yaml
Type: SwitchParameter
Parameter Sets: DiscoverByService
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DomainName
Specifies the domain to search.
The cmdlet locates a discoverable domain controller in this domain.
Specify the domain by using the NetBIOS name or Fully Qualified Domain Name (FQDN) of the domain.

```yaml
Type: String
Parameter Sets: DiscoverByService
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Filter
Specifies a query string that retrieves Active Directory objects.
This string uses the Windows PowerShell Expression Language syntax.
The Windows PowerShell Expression Language syntax provides rich type-conversion support for value types received by the *Filter* parameter.
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

### -ForceDiscover
Indicates that the cmdlet to clears any cached domain controller information and perform a new discovery.
If this parameter is not specified the cmdlet may return cached domain controller information.

```yaml
Type: SwitchParameter
Parameter Sets: DiscoverByService
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Identity
Specifies an Active Directory domain controller object by providing one of the following values.
The identifier in parentheses is the LDAP display name for the attribute.
Unless specified otherwise, these values are for the server object that represents the domain controller.
The acceptable values for this parameter are:

- A GUID (objectGUID)
- An IPV4Address
- A Global IPV6Address
- A DNS Host Name (dNSHostName)
- The name of the server object
- The distinguished name of the NTDS Settings object
- The distinguished name of the server object that represents the domain controller
- The GUID of NTDS settings object under the configuration partition
- The GUID of server object under the configuration partition
- The distinguished name of the computer object that represents the domain controller

The cmdlet searches the default naming context or partition to find the object.
If two or more objects are found, the cmdlet returns a non-terminating error.

This parameter can also get this object through the pipeline or you can set this parameter to an object instance.

```yaml
Type: ADDomainController
Parameter Sets: Identity
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -MinimumDirectoryServiceVersion
Species the earliest operating system that the domain controller can have so that it is returned by the cmdlet when getting a domain controller using *Discover* parameter.
The acceptable values for this parameter are:

- Windows2000 or 1
- Windows2008 or 2

```yaml
Type: ADMinimumDirectoryServiceVersion
Parameter Sets: DiscoverByService
Aliases:
Accepted values: Windows2000, Windows2008, Windows2012, Windows2012R2

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NextClosestSite
Specifies to return a domain controller in the next closest site when a domain controller is not found in the site that contains the client.
The next closest site is the site with the lowest site link cost with respect to the current site.
Costs between sites are based on factors such as bandwidth, as well as physical proximity.

```yaml
Type: SwitchParameter
Parameter Sets: DiscoverByService
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
Parameter Sets: Identity, Filter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Service
Species the types of domain controllers to get.
You can specify more than one type by using a comma-separated list.
The acceptable values for this parameter are:

- PrimaryDC or 1
- GlobalCatalog or 2
- KDC or 3
- TimeService or 4
- ReliableTimeService or 5
- ADWS or 6

```yaml
Type: ADDiscoverableService[]
Parameter Sets: DiscoverByService
Aliases:
Accepted values: PrimaryDC, GlobalCatalog, KDC, TimeService, ReliableTimeService, ADWS

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SiteName
Specifies the name of a site to search in to find the domain controller.
If this parameter is not set, the cmdlet searches for domain controllers in the same site as the client.
The name of the site is defined by the **Name** property of the site object.

```yaml
Type: String
Parameter Sets: DiscoverByService
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Writable
Specifies whether this is a writable domain controller.

```yaml
Type: SwitchParameter
Parameter Sets: DiscoverByService
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

### Microsoft.ActiveDirectory.Management.ADDomainController
A domain controller object is received by the *Identity* parameter.

## OUTPUTS

### Microsoft.ActiveDirectory.Management.ADDomainController
This cmdlet returns one or more domain controller objects.

When you use the *Discover* parameter to get a domain controller, the cmdlet returns a default set of property values for each domain controller.

When you use the *Identity* or *Filter* parameters to get a domain controller, this cmdlet returns all of the properties of the domain controller.

To view all of the properties for an **ADDomainController** object, use the following command and replace \<domaincontroller\> with a domain controller identifier such as a DNS host name.

`Get-ADDomainController`\<domaincontroller\>`| Get-Member`

## NOTES
* The **Name** and **HostName** properties of the **ADDomainController** objects returned by the cmdlet are set according to the following rules:

  - If the *Discover* parameter is used, HostName is the Fully Qualified Domain Name of the Domain Controller, and the Name is the NetBIOS name of the Domain Controller.
With the *Discover* parameter, the cmdlet will perform a second DCLocator call, to populate the **Name** property.
This property will not be set, to the NetBIOS name of the Domain Controller, if the WINS service is unavailable.

  - If the *Identity* or the *Filter* parameter is used, **HostName** is the **DNSHostName** attribute of the Domain Controller object, and the **Name** is the **Name** (RDN) attribute of the Domain Controller object.
With the *Identity* or the *Filter* parameter, the **HostName** property will not be set, if the **DNSHostName** attribute of the Domain Controller object is null.

* This cmdlet does not work with Active Directory Lightweight Directory Services (AD LDS).
* This cmdlet does not work when targeting a snapshot using the *Server* parameter.

## RELATED LINKS

[Add-ADDomainControllerPasswordReplicationPolicy](./Add-ADDomainControllerPasswordReplicationPolicy.md)

[Get-ADDomainControllerPasswordReplicationPolicy](./Get-ADDomainControllerPasswordReplicationPolicy.md)

[Remove-ADDomainControllerPasswordReplicationPolicy](./Remove-ADDomainControllerPasswordReplicationPolicy.md)
