---
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
Module Name: ActiveDirectory
online version: https://learn.microsoft.com/powershell/module/activedirectory/get-addomain?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-ADDomain

## SYNOPSIS
Gets an Active Directory domain.

## SYNTAX

### Current (Default)
```
Get-ADDomain [-AuthType <ADAuthType>] [-Credential <PSCredential>] [-Current <ADCurrentDomainType>]
 [-Server <String>] [<CommonParameters>]
```

### Identity
```
Get-ADDomain [-AuthType <ADAuthType>] [-Credential <PSCredential>] [-Identity] <ADDomain> [-Server <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The Get-ADDomain cmdlet gets the Active Directory domain specified by the parameters.
You can specify the domain by setting the Identity or Current parameters.

The Identity parameter specifies the Active Directory domain to get.
You can identify the domain object to get by its Distinguished Name (DN), GUID, Security Identifier (SID), DNS domain name, or NetBIOS name.
You can also set the parameter to a domain object variable, such as $\<localDomainObject\> or pass a domain object through the pipeline to the Identity parameter.

To get the domain of the local computer or current logged on user (CLU) set the Current parameter to LocalComputer or LoggedOnUser. 
When you set the Current parameter, you do not need to set the Identity parameter.

When the Current parameter is set to LocalComputer or LoggedOnUser, the cmdlet uses the Server and Credential parameters according to the following rules.

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
C:\PS>Get-ADDomain fabrikam.com
```

Description

-----------

Gets the domain information for the domain 'fabrikam.com'.

### -------------------------- EXAMPLE 2 --------------------------
```
C:\PS>Get-ADDomain -Current LocalComputer
```

Description

-----------

Get the domain information of the current local computer domain.

### -------------------------- EXAMPLE 3 --------------------------
```
C:\PS>Get-ADDomain -Current LoggedOnUser
```

Description

-----------

Gets the domain information for the domain of the currently logged on user.

### -------------------------- EXAMPLE 4 --------------------------
```
C:\PS>Get-ADDomain

AllowedDNSSuffixes                 : {}
ChildDomains                       : {}
ComputersContainer                 : CN=Computers,DC=Fabrikam,DC=com
DeletedObjectsContainer            : CN=Deleted Objects,DC=Fabrikam,DC=com
DistinguishedName                  : DC=Fabrikam,DC=com
DNSRoot                            : Fabrikam.com
DomainControllersContainer         : OU=Domain Controllers,DC=Fabrikam,DC=com
DomainMode                         : Windows2003Domain
DomainSID                          : S-1-5-21-41432690-3719764436-1984117282
ForeignSecurityPrincipalsContainer : CN=ForeignSecurityPrincipals,DC=Fabrikam,DC=com
Forest                             : Fabrikam.com
InfrastructureMaster               : Fabrikam-DC1.Fabrikam.com
LastLogonReplicationInterval       :
LinkedGroupPolicyObjects           : {CN={31B2F340-016D-11D2-945F-00C04FB984F9},CN=Policies,CN=System,DC=Fabrikam,DC=com}
LostAndFoundContainer              : CN=LostAndFound,DC=Fabrikam,DC=com
ManagedBy                          :
Name                               : Fabrikam
NetBIOSName                        : FABRIKAM
ObjectClass                        : domainDNS
ObjectGUID                         : b63b4f44-58b9-49cf-8911-b36e8575d5eb
ParentDomain                       :
PDCEmulator                        : Fabrikam-DC1.Fabrikam.com
QuotasContainer                    : CN=NTDS Quotas,DC=Fabrikam,DC=com
ReadOnlyReplicaDirectoryServers    : {CSD2722780.Fabrikam.com}
ReplicaDirectoryServers            : {Fabrikam-DC1.Fabrikam.com}
RIDMaster                          : Fabrikam-DC1.Fabrikam.com
SubordinateReferences              : {DC=ForestDnsZones,DC=Fabrikam,DC=com, DC=DomainDnsZones,DC=Fabrikam,DC=com, CN=Co
nfiguration,DC=Fabrikam,DC=com}
SystemsContainer                   : CN=System,DC=Fabrikam,DC=com
UsersContainer                     : CN=Users,DC=Fabrikam,DC=com
```

Description

-----------

Gets the domain information for the domain of the currently logged on user.

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
Type: ADCurrentDomainType
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
Specifies an Active Directory domain object by providing one of the following property values.
The identifier in parentheses is the LDAP display name for the attribute.
All values are for the domainDNS object that represents the domain.

Distinguished Name

Example: DC=redmond,DC=corp,DC=contoso,DC=com

GUID (objectGUID)

Example: 599c3d2e-f72d-4d20-8a88-030d99495f20

Security Identifier (objectSid)

Example: S-1-5-21-3165297888-301567370-

DNS domain name

Example: redmond.corp.contoso.com

NetBIOS domain name

Example: redmond

The cmdlet searches the default naming context or partition to find the object.
If two or more objects are found, the cmdlet returns a non-terminating error.

This parameter can also get this object through the pipeline or you can set this parameter to a domain object instance.

This example shows how to set the parameter to a distinguished name.

-Identity  "DC=redmond,DC=corp,DC=contoso,DC=com"

This example shows how to set this parameter to a domain object instance named "domainInstance".

-Identity   $domainInstance

```yaml
Type: ADDomain
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

### None or Microsoft.ActiveDirectory.Management.ADDomain
A domain object is received by the Identity parameter.

## OUTPUTS

### Microsoft.ActiveDirectory.Management.ADDomain
Returns one or more domain objects.

The cmdlet returns all of the properties of the domain.
To view all of the properties for an ADDomain object, use the following command and replace \<domain\> with a domain controller identifier such as a DNS host name.

Get-ADDomain \<domain\>| Get-Member

## NOTES
* This cmdlet does not work with AD LDS.

  This cmdlet does not work when targeting a snapshot using the Server parameter.

## RELATED LINKS

[Set-ADDomain](./Set-ADDomain.md)

[Set-ADDomainMode](./Set-ADDomainMode.md)

