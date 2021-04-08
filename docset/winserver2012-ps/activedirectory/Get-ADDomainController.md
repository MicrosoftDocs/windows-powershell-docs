---
author: Kateyanne
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
manager: dansimp
Module Name: ActiveDirectory
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/activedirectory/get-addomaincontroller?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
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
The Get-ADDomainController cmdlet gets the domain controllers specified by the parameters.
You can get domain controllers by setting the Identity, Filter or Discover parameters.

The Identity parameter specifies the domain controller to get.
You can identify a domain controller by its GUID, IPV4Address, global IPV6Address, or DNS host name.
You can also identify a domain controller by the name of the server object that represents the domain controller, the Distinguished Name (DN) of the NTDS settings object or the server object, the GUID of the NTDS settings object or the server object under the configuration partition, or the DN of the computer object that represents the domain controller. 
You can also set the Identity parameter to a domain controller object variable, such as $\<localDomainControllerObject\>, or pass a domain controller object through the pipeline to the Identity parameter.

To search for and retrieve more than one domain controller, use the Filter parameter.
The Filter parameter uses the PowerShell Expression Language to write query strings for Active Directory.
PowerShell Expression Language syntax provides rich type conversion support for value types received by the Filter parameter.
For more information about the Filter parameter syntax, see about_ActiveDirectory_Filter.
You cannot use an LDAP query string with this cmdlet.

To get a domain controller by using the discovery mechanism of DCLocator, use the Discover parameter.
You can provide search criteria by setting parameters such as Service, SiteName, DomainName, NextClosestSite, AvoidSelf, and ForceDiscover.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
C:\PS>Get-ADDomainController -Discover -Site "Default-First-Site-Name"
```

Description

-----------

Get one available DC in a given site using Discovery.

### -------------------------- EXAMPLE 2 --------------------------
```
C:\PS>Get-ADDomainController -Discover -Site "Default-First-Site-Name" -ForceDiscover
```

Description

-----------

Force discover/find one available DC in a given site.

### -------------------------- EXAMPLE 3 --------------------------
```
C:\PS>Get-ADDomainController -Discover -Service "GlobalCatalog"
```

Description

Get a global catalog in the current forest using Discovery. Domain type name is used in this scenario.

-----------

### -------------------------- EXAMPLE 4 --------------------------
```
C:\PS>Get-ADDomainController -Discover -Service 2
```

Description

-----------

Get a global catalog in the current forest using Discovery. Domain type id is used in this scenario. 

### -------------------------- EXAMPLE 5 --------------------------
```
C:\PS>Get-ADDomainController -Discover
```

Description

-----------

Get one available DC in the current domain using Discovery.

### -------------------------- EXAMPLE 6 --------------------------
```
C:\PS>Get-ADDomainController -Discover -Domain "fabrikam.com"
```

Description

-----------

Get one available DC in a given domain using Discovery.

### -------------------------- EXAMPLE 7 --------------------------
```
C:\PS>Get-ADDomainController -Discover -Domain "corp.contoso.com" -Service "PrimaryDC","TimeService"
```

Description

-----------

Get the PDC using Discovery and make sure that is advertising as a time server.

### -------------------------- EXAMPLE 8 --------------------------
```
C:\PS>Get-ADDomainController -Identity "PDC-01"
```

Description

-----------

Get a domain controller using its NetBIOS name.

### -------------------------- EXAMPLE 9 --------------------------
```
C:\PS>Get-ADDomainController "PDC-01"
```

Description

-----------

Get a domain controller using its NetBIOS name.

### -------------------------- EXAMPLE 10 --------------------------
```
C:\PS>Get-ADDomainController -Identity "TK5-CORP-DC-10.fabrikam.com" -Server "fabrikam.com" -Credential "corp\administrator"
```

Description

-----------

Get a domain controller using its DNS host name, in a given domain (specified in Server parameter) and specifying administrator credentials.

### -------------------------- EXAMPLE 11 --------------------------
```
C:\PS>Get-ADDomainController -Identity "168.54.62.57"
```

Description

-----------

Get a domain controller using its IP address.

### -------------------------- EXAMPLE 12 --------------------------
```
C:\PS>Get-ADDomainController -Filter "isGlobalCatalog -eq `$true -and Site -eq 'Default-First-Site-Name'"
```

Description

-----------

Get all global catalogs in a given site.

### -------------------------- EXAMPLE 13 --------------------------
```
C:\PS>Get-ADDomainController -Server "research.fabrikam.com" -Filter "isGlobalCatalog -eq `$true -and isReadOnly -eq `$true"
```

Description

-----------

Get all ROGCs in the child domain to which the client is connected.

### -------------------------- EXAMPLE 14 --------------------------
```
C:\PS>Get-ADDomainController
```

Description

-----------

Gets the domain controller in the user's current session.
This is the domain controller used as a default Server in the context of an AD Provider.
Using this cmdlet in this way will let you know which Server is being used by default.

### -------------------------- EXAMPLE 15 --------------------------
```
C:\PS>$allDCs = (Get-ADForest).Domains | %{ Get-ADDomainController -Filter * -Server $_ }
```

Description

-----------

Gets a list of all of the domain controllers for all the domains within a forest.

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

### -AvoidSelf
Specifies to not return the current computer as a domain controller.
If the current computer is not a domain controller, this parameter is ignored.
You can specify this parameter when you want to get the name of another domain controller in the domain.

The following example shows how to specify this parameter.

-AvoidSelf

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

To get a domain controller by using the discovery mechanism of DCLocator, use the Discover parameter.
Along with this parameter, you can provide search criteria by setting parameters such as Service, SiteName, DomainName, NextClosestSite, AvoidSelf, and ForceDiscover.

The following example shows how to specify this parameter.

-Discover

The following example shows how to get a live DC that has Web Services enabled in a specific site with name "RODC-Site".

Get-ADDomainController -Discover -Services ADWS -SiteName RODC-Site

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

The following example shows how to set this parameter to the FQDN of a domain.

-DomainName "contoso.com"

```yaml
Type: String
Parameter Sets: DiscoverByService
Aliases: 

Required: False
Position: Named
Default value: Name of the domain to which this machine is joined
Accept pipeline input: False
Accept wildcard characters: False
```

### -Filter
Specifies a query string that retrieves Active Directory objects.
This string uses the PowerShell Expression Language syntax.
The PowerShell Expression Language syntax provides rich type-conversion support for value types received by the Filter parameter.
The syntax uses an in-order representation, which means that the operator is placed between the operand and the value.
For more information about the Filter parameter, see about_ActiveDirectory_Filter.

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

For a list of supported types for \<value\>, see about_ActiveDirectory_ObjectModel.

Examples:

The following examples show how to use this syntax with Active Directory cmdlets.

To get all objects of the type specified by the cmdlet, use the asterisk wildcard:

All user objects:

Get-ADUser -Filter *

-or-

All computer objects:

Get-ADComputer -Filter *

To get all user objects that have an e-mail message attribute, use one of the following commands:

Get-ADUser -Filter "EmailAddress -like '*'"

Get-ADUser -Filter "mail -like '*'"

-or-

Get-ADObject -Filter "(mail -like '*') -and (ObjectClass -eq 'user')"

Note: PowerShell wildcards other than "*", such as "?" are not supported by the Filter syntax.

To get all users objects that have surname of Smith and that have an e-mail attribute, use one of the following commands:

Get-ADUser -filter "(EmailAddress -like '*') -and (Surname -eq 'smith')"

-or-

Get-ADUser -filter "(mail -eq '*') -and (sn -eq 'Smith')"

To get all user objects who have not logged on since January 1, 2007, use the following commands:

$logonDate = New-Object System.DateTime(2007, 1, 1)

Get-ADUser -filter "lastLogon -le '$logonDate'"

To get all groups that have a group category of Security and a group scope of Global, use one of the following commands:

Get-ADGroup -filter "GroupCategory -eq 'Security' -and GroupScope -eq 'Global'"

-or-

Get-ADGroup -filter "GroupType -band 0x80000000"

Note: To query using LDAP query strings, use the LDAPFilter parameter.

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
Forces the cmdlet to clear any cached domain controller information and perform a new discovery. 
If this parameter is not specified the cmdlet  may return cached domain controller information.

The following example shows how to set this parameter.

-ForceDiscover

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

GUID (objectGUID)

Example: 768c44de-f72d-66e0-8a88-0523ca495f20

IPV4Address

Example:157.59.132.61

Global IPV6Address

Example: 2001:4898:0:fff:200:5efe:157.59.132.61

DNS Host Name (dNSHostName)

Example: corp-DC01.corp.contoso.com

Name of the server object

Example: corp-DC01$

Distinguished Name of the NTDS Settings object

Example: CN=NTDS Settings,CN=CORP-DC12,CN=Servers,CN=NA-CAN-QBC,CN=Sites,CN=Configuration,DC=corp,DC=contoso

Distinguished Name of the server object that represents the domain controller

Example: CN=CORP-DC12,CN=Servers,CN=NA-CAN-QBC,CN=Sites,CN=Configuration,DC=corp,DC=contoso,DC=com

GUID of NTDS settings object under the configuration partition

Example: 68adaf21-e28d-6012-bca8-320d93450ab0

GUID of server object under the configuration partition

Example: 599c3d2e-f72d-4d20-8a88-030d99495f20

Distinguished Name of the computer object that represents the domain controller.

Example: CN=CORP-DC12,OU=Domain Controllers,DC=corp,DC=contoso,DC=com

The cmdlet searches the default naming context or partition to find the object.
If two or more objects are found, the cmdlet returns a non-terminating error.

This parameter can also get this object through the pipeline or you can set this parameter to an object instance.

This example shows how to set the parameter to a distinguished name of the NTDS Settings object.

-Identity "CN=NTDS Settings,CN=CORP-DC12,CN=Servers,CN=NA-CAN-QBC,CN=Sites,CN=Configuration,DC=corp,DC=contoso"

This example shows how to set this parameter to a domain controller object instance named "AD_DCInstance".

-Identity $AD_DCInstance

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
Species the earliest operating system that the domain controller can have so that it is returned by the cmdlet when getting a DC using -Discover switch.
Possible values are:

Windows2000 or 1

Windows2008 or 2

The following example shows how to set this parameter.

-MinimumDirectoryServiceVersion Windows2000

The following example shows how to get any live DC that is Windows 2008 or above:

Get-ADDomainController -Discover -MinimumDirectoryServiceVersion Windows2008

```yaml
Type: ADMinimumDirectoryServiceVersion
Parameter Sets: DiscoverByService
Aliases: 
Accepted values: Windows2000, Windows2008, Windows2012

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

The following example shows how to specify this parameter.

-NextClosestSite

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
Possible values for this parameter are:

PrimaryDC or 1

GlobalCatalog or 2

KDC or 3

TimeService or 4

ReliableTimeService or 5

ADWS or 6

The following example shows how to set this parameter.

-Service GlobalCatalog, KDC

The following example shows how to get a live DC that has Web Services enabled:

Get-ADDomainController -Discover -Services ADWS

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
The name of the site is defined by the Name property of the site object.

The following example shows how to use this parameter to specify a site.

-SiteName "redmond"

```yaml
Type: String
Parameter Sets: DiscoverByService
Aliases: 

Required: False
Position: Named
Default value: Name of the site that the client is in
Accept pipeline input: False
Accept wildcard characters: False
```

### -Writable
Specifies whether or not this is a writable domain controller.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.ActiveDirectory.Management.ADDomainController
A domain controller object is received by the Identity parameter.

## OUTPUTS

### Microsoft.ActiveDirectory.Management.ADDomainController
Returns one or more domain controller objects.

When you use the Discover parameter to get a domain controller, the cmdlet returns a default set of property values for each domain controller.

When you use the Identity or Filter parameters to get a domain controller, this cmdlet returns all of the properties of the domain controller.

To view all of the properties for an ADDomainController object, use the following command and replace \<domaincontroller\> with a domain controller identifier such as a DNS host name.

Get-ADDomainController \<domaincontroller\>| Get-Member

## NOTES
* The Name and HostName properties of the ADDomainController objects returned by the cmdlet are set according to the following rule:

  - If the Discover parameter is used, HostName is the Fully Qualified Domain Name of the Domain Controller, and the Name is the NetBIOS name of the Domain Controller.
With the Discover parameter, the cmdlet will perform a second DCLocator call, to populate the Name property.
This property will not be set, to the NetBIOS name of the Domain Controller, if the WINS service is unavailable.

  - If the Identity or the Filter parameter is used, HostName is the DNSHostName attribute of the Domain Controller object, and the Name is the Name (RDN) attribute of the Domain Controller object.
With the Identity or the Filter parameter, the HostName property will not be set, if the DNSHostName attribute of the Domain Controller object is null.

  This cmdlet does not work with AD LDS.

  This cmdlet does not work when targeting a snapshot using the Server parameter.

## RELATED LINKS

[Add-ADDomainControllerPasswordReplicationPolicy](./Add-ADDomainControllerPasswordReplicationPolicy.md)

[Get-ADDomainControllerPasswordReplicationPolicy](./Get-ADDomainControllerPasswordReplicationPolicy.md)

[Remove-ADDomainControllerPasswordReplicationPolicy](./Remove-ADDomainControllerPasswordReplicationPolicy.md)

