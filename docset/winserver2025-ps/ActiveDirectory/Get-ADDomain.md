---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
Module Name: ActiveDirectory
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/activedirectory/get-addomain?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ADDomain
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
The **Get-ADDomain** cmdlet gets the Active Directory domain specified by the parameters.
You can specify the domain by setting the *Identity* or *Current* parameters.

The *Identity* parameter specifies the Active Directory domain to get.
You can identify the domain object to get by its distinguished name, GUID, Security Identifier (SID), DNS domain name, or NetBIOS name.
You can also set the parameter to a domain object variable, such as `$<localDomainObject>` or pass a domain object through the pipeline to the *Identity* parameter.

To get the domain of the local computer or current logged on user set the *Current* parameter to LocalComputer or LoggedOnUser.
When you set the *Current* parameter, you do not need to set the *Identity* parameter.

When the *Current* parameter is set to LocalComputer or LoggedOnUser, the cmdlet uses the *Server* and *Credential* parameters according to the following rules.

- If both the *Server* and *Credential* parameters are not specified:
- The domain is set to the domain of the LocalComputer or LoggedOnUser and a server is located in this domain. The credentials of the current logged on user are used to get the domain.
- If the *Server* parameter is specified and the *Credential* parameter is not specified:
- The domain is set to the domain of the specified server and the cmdlet checks to make sure that the server is in the domain of the LocalComputer or LoggedOnUser. Then the credentials of the current logged on user are used to get the domain. An error is returned when the server is not in the domain of the LocalComputer or LoggedOnUser.
- If the *Server* parameter is not specified and the *Credential* parameter is specified:
- The domain is set to the domain of the LocalComputer or LoggedOnUser and a server is located in this domain. Then the credentials specified by the *Credential* parameter are used to get the domain.
- If the *Server* and *Credential* parameters are specified:
- The domain is set to the domain of the specified server and the cmdlet checks to make sure that the server is in the domain of the LocalComputer or LoggedOnUser. Then the credentials specified by the *Credential* parameter are used to get the domain. An error is returned when the server is not in the domain of the LocalComputer or LoggedOnUser.

## EXAMPLES

### Example 1: Get domain information from Active Directory
```
PS C:\> Get-ADDomain -Identity user.com
```

This command gets the domain information for the domain user.com.

### Example 2: Get domain information of the current local computer domain
```
PS C:\> Get-ADDomain -Current LocalComputer
```

This command gets the domain information of the current local computer domain.

### Example 3: Get domain information for the domain of the currently logged in user
```
PS C:\> Get-ADDomain -Current LoggedOnUser
```

This command gets the domain information for the domain of the currently logged on user.

### Example 4: Get domain information for the domain of the currently logged in user
```
PS C:\> Get-ADDomain
AllowedDNSSuffixes                 : {}
ChildDomains                       : {}
ComputersContainer                 : CN=Computers,DC=User04,DC=com
DeletedObjectsContainer            : CN=Deleted Objects,DC=User04,DC=com
DistinguishedName                  : DC=User04,DC=com
DNSRoot                            : User04.com
DomainControllersContainer         : OU=Domain Controllers,DC=User04,DC=com
DomainMode                         : Windows2003Domain
DomainSID                          : S-1-5-21-41432690-3719764436-1984117282
ForeignSecurityPrincipalsContainer : CN=ForeignSecurityPrincipals,DC=User04,DC=com
Forest                             : User04.com
InfrastructureMaster               : User04-DC1.User04.com
LastLogonReplicationInterval       :
LinkedGroupPolicyObjects           : {CN={31B2F340-016D-11D2-945F-00C04FB984F9},CN=Policies,CN=System,DC=User04,DC=com}
LostAndFoundContainer              : CN=LostAndFound,DC=User04,DC=com
ManagedBy                          :
Name                               : User04
NetBIOSName                        : USER04
ObjectClass                        : domainDNS
ObjectGUID                         : b63b4f44-58b9-49cf-8911-b36e8575d5eb
ParentDomain                       :
PDCEmulator                        : User04-DC1.User04.com
QuotasContainer                    : CN=NTDS Quotas,DC=User04,DC=com
ReadOnlyReplicaDirectoryServers    : {CSD2722780.User04.com}
ReplicaDirectoryServers            : {User04-DC1.User04.com}
RIDMaster                          : User04-DC1.User04.com
SubordinateReferences              : {DC=ForestDnsZones,DC=User04,DC=com, DC=DomainDnsZones,DC=User04,DC=com, CN=Co
nfiguration,DC=User04,DC=com}
SystemsContainer                   : CN=System,DC=User04,DC=com
UsersContainer                     : CN=Users,DC=User04,DC=com
```

This command gets the domain information for the domain of the currently logged on user.

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

### -Current
Specifies whether to return the domain of the local computer or the current logged on user.
The acceptable values for this parameter are:

- LocalComputer or 0
- LoggedOnUser  or 1

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
The identifier in parentheses is the Lightweight Directory Access Protocol (LDAP) display name for the attribute.
All values are for the **domainDNS** object that represents the domain.
The acceptable values for this parameter are:

- A distinguished name
- A GUID (objectGUID)
- A security identifier (objectSid)
- A DNS domain name
- A NetBIOS domain name

The cmdlet searches the default naming context or partition to find the object.
If two or more objects are found, the cmdlet returns a non-terminating error.

This parameter can also get this object through the pipeline or you can set this parameter to a domain object instance.

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

- By using the **Server** value from objects passed through the pipeline
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

### None or Microsoft.ActiveDirectory.Management.ADDomain
A domain object is received by the *Identity* parameter.

## OUTPUTS

### Microsoft.ActiveDirectory.Management.ADDomain
This cmdlet returns one or more domain objects.

The cmdlet returns all of the properties of the domain.
To view all of the properties for an **ADDomain** object, use the following command and replace \<domain\> with a domain controller identifier such as a DNS host name.

`Get-ADDomain`\<domain\>`| Get-Member`

## NOTES
* This cmdlet does not work with Active Directory Lightweight Directory Services (AD LDS).
* This cmdlet does not work when targeting a snapshot using the *Server* parameter.

## RELATED LINKS

[Set-ADDomain](./Set-ADDomain.md)

[Set-ADDomainMode](./Set-ADDomainMode.md)

