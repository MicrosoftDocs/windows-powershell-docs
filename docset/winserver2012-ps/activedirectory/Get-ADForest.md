---
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
Module Name: ActiveDirectory
online version: https://learn.microsoft.com/powershell/module/activedirectory/get-adforest?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-ADForest

## SYNOPSIS
Gets an Active Directory forest.

## SYNTAX

### Current (Default)
```
Get-ADForest [-AuthType <ADAuthType>] [-Credential <PSCredential>] [-Current <ADCurrentForestType>]
 [-Server <String>] [<CommonParameters>]
```

### Identity
```
Get-ADForest [-AuthType <ADAuthType>] [-Credential <PSCredential>] [-Identity] <ADForest> [-Server <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The Get-ADForest cmdlet gets the Active Directory forest specified by the parameters.
You can specify the forest by setting the Identity or Current parameters.

The Identity parameter specifies the Active Directory forest to get.
You can identify a forest by its fully qualified domain name (FQDN), DNS host name, or NetBIOS name.
You can also set the parameter to a forest object variable, such as $\<localForestObject\> or you can pass a forest object through the pipeline to the Identity parameter.

To retrieve the forest of the local computer or current logged on user (CLU) set the Current parameter to LocalComputer or LoggedOnUser. 
When you set the Current parameter, you do not need to set the Identity parameter.

When the Current parameter is set to LocalComputer or LoggedOnUser, the cmdlet uses the Server and Credential parameter values to determine the domain and the credentials to use to identify the domain of the forest according to the following rules.

-If both the Server and Credential parameters are not specified:

- The domain is set to the domain of the LocalComputer or LoggedOnUser and a server is located in this domain. The credentials of the current logged on user are used to get the domain.

-If the Server parameter is specified and the Credential parameter is not specified:

- The domain is set to the domain of the specified server and the cmdlet checks to make sure that the server is in the domain of the LocalComputer or LoggedOnUser. Then the credentials of the current logged on user are used to get the domain. An error is returned when the server is not in the domain of the LocalComputer or LoggedOnUser.

-If the Server parameter is not specified and the Credential parameter is specified:

- The domain is set to the domain of the LocalComputer or LoggedOnUser and a server is located in this domain. Then the credentials specified by the Credential parameter are used to get the domain.

If the Server and Credential parameters are specified:

The domain is set to the domain of the specified server and the cmdlet checks to make sure that the server is in the domain of the LocalComputer or LoggedOnUser.
Then the credentials specified by the Credential parameter are used to get the domain.
An error is returned when the server is not in the domain of the LocalComputer or LoggedOnUser.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
C:\PS>Get-ADForest Fabrikam.com
```

Description

-----------

Get the forest information of the Fabrikam.com forest.

### -------------------------- EXAMPLE 2 --------------------------
```
C:\PS>Get-ADForest -Current LocalComputer
```

Description

-----------

Get the forest information of the current local computer's forest.

### -------------------------- EXAMPLE 3 --------------------------
```
C:\PS>Get-ADForest -Current LoggedOnUser
```

Description

-----------

Get the forest information of the current logged on users's forest.

### -------------------------- EXAMPLE 4 --------------------------
```
C:\PS>Get-ADForest
ApplicationPartitions  : {DC=ForestDnsZones,DC=Fabrikam,DC=com, DC=DomainDnsZones,DC=Fabrikam,DC=com}
CrossForestReferences  : {CN=northwind,CN=Partitions,CN=Configuration,DC=Fabrikam,DC=com}
DomainNamingMaster     : Fabrikam-DC1.Fabrikam.com
Domains                : {Fabrikam.com}
ForestMode             : Windows2003Forest
GlobalCatalogs         : {Fabrikam-DC1.Fabrikam.com, CSD2722780.Fabrikam.com}
Name                   : Fabrikam.com
PartitionsContainer    : CN=Partitions,CN=Configuration,DC=Fabrikam,DC=com
RootDomain             : Fabrikam.com
SchemaMaster           : Fabrikam-DC1.Fabrikam.com
Sites                  : {Default-First-Site-Name, UnitedKingdomHQ, BO3, RODC-Site-Name}
SPNSuffixes            : {}
UPNSuffixes            : {}
```

Description

-----------

Gets the forest information for the forest of the currently logged on user.

### -------------------------- EXAMPLE 5 --------------------------
```
C:\PS>$allDCs = (Get-ADForest).Domains | %{ Get-ADDomainController -Filter * -Server $_ }
```

Description

-----------

Gets a list of all the domain controllers for all domain within a forest.

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

### -Current
Specifies whether to return the domain of the local computer or the current logged on user (CLU).
Possible values for this parameter are:

LocalComputer or 0

LoggedOnUser  or 1

The following example shows how to set this parameter to return the domain of the current logged on user.

-Current LoggedOnUser

```yaml
Type: ADCurrentForestType
Parameter Sets: Current
Aliases: 
Accepted values: LocalComputer, LoggedOnUser

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Identity
Specifies an Active Directory forest object by providing one of the following attribute values.
The identifier in parentheses is the LDAP display name for the attribute.

Fully qualified domain name

Example: corp.contoso.com

GUID (objectGUID)

Example: 599c3d2e-f72d-4d20-8a88-030d99495f20

DNS host name

Example: dnsServer.corp.contoso.com

NetBIOS name

Example: corp

The cmdlet searches the default naming context or partition to find the object.
If two or more objects are found, the cmdlet returns a non-terminating error.

This parameter can also get this object through the pipeline or you can set this parameter to a forest object instance.

This example shows how to set the parameter to a fully qualified domain name.

-Identity "corp.contoso.com"

This example shows how to set this parameter to a forest object instance named "forestInstance".

-Identity $forestInstance

```yaml
Type: ADForest
Parameter Sets: Identity
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
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

### None or Microsoft.ActiveDirectory.Management.ADForest
A forest object is received by the Identity parameter.

## OUTPUTS

### Microsoft.ActiveDirectory.Management.ADForest
Returns one or more forest objects.

This cmdlet returns all of the properties of the forest.
To view all of the properties for an ADForest object, use the following command and replace \<forest\> with a forest identifier such as a DNS host name.

Get-ADForest \<forest\>| Get-Member

## NOTES
* This cmdlet does not work with AD LDS.

  This cmdlet does not work when targeting a snapshot using the Server parameter.

## RELATED LINKS

[Set-ADForest](./Set-ADForest.md)

[Set-ADForestMode](./Set-ADForestMode.md)

