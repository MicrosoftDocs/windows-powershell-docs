---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
Module Name: ActiveDirectory
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/activedirectory/get-adrootdse?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ADRootDSE
---

# Get-ADRootDSE

## SYNOPSIS
Gets the root of a directory server information tree.

## SYNTAX

```
Get-ADRootDSE [-AuthType <ADAuthType>] [-Credential <PSCredential>] [-Properties <String[]>] [-Server <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-ADRootDSE** cmdlet gets the object that represents the root of the directory information tree of a directory server.
This tree provides information about the configuration and capabilities of the directory server, such as the distinguished name for the configuration container, the current time on the directory server, and the functional levels of the directory server and the domain.

## EXAMPLES

### Example 1: Get the root of a directory server information tree
```
PS C:\> Get-ADRootDSE
configurationNamingContext    : CN=Configuration,DC=Fabrikam,DC=com
currentTime                   : 3/18/2009 11:12:55 AM
defaultNamingContext          : DC=Fabrikam,DC=com
dnsHostName                   : FABRIKAM-DC1.Fabrikam.com
domainControllerFunctionality : Windows2008R2
domainFunctionality           : Windows2003Domain
dsServiceName                 : CN=NTDS Settings,CN=FABRIKAM-DC1,CN=Servers,CN=Default-First-Site-Name,CN=Sites,CN=Configuration,DC=Fabrikam,DC=com
forestFunctionality           : Windows2003Forest
highestCommittedUSN           : 23015
isGlobalCatalogReady          : {TRUE}
isSynchronized                : {TRUE}
ldapServiceName               : Fabrikam.com:FABRIKAM-DC1$@FABRIKAM.COM
namingContexts                : {DC=Fabrikam,DC=com, CN=Configuration,DC=Fabrikam,DC=com, CN=Schema,CN=Configuration,DC=Fabrikam,DC=com, DC=DomainDnsZones,DC=Fabrikam,DC=com...}
rootDomainNamingContext       : DC=Fabrikam,DC=com
schemaNamingContext           : CN=Schema,CN=Configuration,DC=Fabrikam,DC=com
serverName                    : CN=FABRIKAM-DC1,CN=Servers,CN=Default-First-Site-Name,CN=Sites,CN=Configuration,DC=Fabrikam,DC=com
subschemaSubentry             : CN=Aggregate,CN=Schema,CN=Configuration,DC=Fabrikam,DC=com
supportedCapabilities         : {1.2.840.113556.1.4.800 (LDAP_CAP_ACTIVE_DIRECTORY_OID), 1.2.840.113556.1.4.1670 (LDAP_CAP_ACTIVE_DIRECTORY_V51_OID), 1.2.840.113556.1.4.1791 (LDAP_CAP_ACTIVE_DIRECTORY_LDAP_INTEG_OID), 1.2.840.113556.1.4.1935 (LDAP_CAP_ACTIVE_DIRECTORY_V61_OID)...}
supportedControl              : {1.2.840.113556.1.4.319 (LDAP_PAGED_RESULT_OID_STRING), 1.2.840.113556.1.4.801 (LDAP_SERVER_SD_FLAGS_OID), 1.2.840.113556.1.4.473 (LDAP_SERVER_SORT_OID), 1.2.840.113556.1.4.528 (LDAP_SERVER_NOTIFICATION_OID)...}
supportedLDAPPolicies         : {MaxPoolThreads, MaxDatagramRecv, MaxReceiveBuffer, InitRecvTimeout...}
supportedLDAPVersion          : {3, 2}
supportedSASLMechanisms       : {GSSAPI, GSS-SPNEGO, EXTERNAL, DIGEST-MD5}
```

This command gets the root of the directory server information tree of the directory server from the default domain controller.

### Example 2: Get the root of the directory server information tree with the specified property
```
PS C:\> Get-ADRootDSE -Server Fabrikam-RODC1 -Properties supportedExtension
configurationNamingContext    : CN=Configuration,DC=Fabrikam,DC=com
currentTime                   : 3/18/2009 11:12:55 AM
defaultNamingContext          : DC=Fabrikam,DC=com
dnsHostName                   : FABRIKAM-RODC1.Fabrikam.com
domainControllerFunctionality : Windows2008R2
domainFunctionality           : Windows2003Domain
dsServiceName                 : CN=NTDS Settings,CN=FABRIKAM-RODC1,CN=Servers,CN=Default-First-Site-Name,CN=Sites,CN=Configuration,DC=Fabrikam,DC=com
forestFunctionality           : Windows2003Forest
highestCommittedUSN           : 23015
isGlobalCatalogReady          : {TRUE}
isSynchronized                : {TRUE}
ldapServiceName               : Fabrikam.com:FABRIKAM-RODC1$@FABRIKAM.COM
namingContexts                : {DC=Fabrikam,DC=com, CN=Configuration,DC=Fabrikam,DC=com, CN=Schema,CN=Configuration,DC=Fabrikam,DC=com, DC=DomainDnsZones,DC=Fabrikam,DC=com...}
rootDomainNamingContext       : DC=Fabrikam,DC=com
schemaNamingContext           : CN=Schema,CN=Configuration,DC=Fabrikam,DC=com
serverName                    : CN=FABRIKAM-RODC1,CN=Servers,CN=Default-First-Site-Name,CN=Sites,CN=Configuration,DC=Fabrikam,DC=com
subschemaSubentry             : CN=Aggregate,CN=Schema,CN=Configuration,DC=Fabrikam,DC=com
supportedCapabilities         : {1.2.840.113556.1.4.800 (LDAP_CAP_ACTIVE_DIRECTORY_OID), 1.2.840.113556.1.4.1670 (LDAP_CAP_ACTIVE_DIRECTORY_V51_OID), 1.2.840.113556.1.4.1791 (LDAP_CAP_ACTIVE_DIRECTORY_LDAP_INTEG_OID), 1.2.840.113556.1.4.1935 (LDAP_CAP_ACTIVE_DIRECTORY_V61_OID)...}
supportedControl              : {1.2.840.113556.1.4.319 (LDAP_PAGED_RESULT_OID_STRING), 1.2.840.113556.1.4.801 (LDAP_SERVER_SD_FLAGS_OID), 1.2.840.113556.1.4.473 (LDAP_SERVER_SORT_OID), 1.2.840.113556.1.4.528 (LDAP_SERVER_NOTIFICATION_OID)...}
supportedExtension            : {1.3.6.1.4.1.1466.20037, 1.3.6.1.4.1.1466.101.119.1, 1.2.840.113556.1.4.1781, 1.3.6.1.4.1.4203.1.11.3}
supportedLDAPPolicies         : {MaxPoolThreads, MaxDatagramRecv, MaxReceiveBuffer, InitRecvTimeout...}
supportedLDAPVersion          : {3, 2}
supportedSASLMechanisms       : {GSSAPI, GSS-SPNEGO, EXTERNAL, DIGEST-MD5}
```

This command gets the root of the directory server information tree including the **supportedExtension** property for Fabrikam-RODC1 server.

### Example 3: Get the root of a directory server information tree by using credentials
```
PS C:\> Get-ADRootDSE -Server "FABRIKAM-ADLDS1.Fabrikam.com:60000" -Credential "FABRIKAM\User1"
configurationNamingContext    : CN=Configuration,CN={9131D98B-E210-480F-A95D-24F9396898CA}
currentTime                   : 3/18/2009 11:40:19 AM
dnsHostName                   : FABRIKAM-ADLDS1.Fabrikam.com
domainControllerFunctionality : Windows2008R2
dsServiceName                 : CN=NTDS Settings,CN=FABRIKAM-ADLDS1$instance1,CN=Servers,CN=Default-First-Site-Name,CN=Sites,C
N=Configuration,CN={9131D98B-E210-480F-A95D-24F9396898CA}
forestFunctionality           : Windows2003Forest
highestCommittedUSN           : 13967
isSynchronized                : {TRUE}
namingContexts                : {CN=Configuration,CN={9131D98B-E210-480F-A95D-24F9396898CA}, CN=Schema,CN=Configuration,CN={9131D98B-E210-480F-A95D-24F9396898CA}, DC=AppNC}
schemaNamingContext           : CN=Schema,CN=Configuration,CN={9131D98B-E210-480F-A95D-24F9396898CA}
serverName                    : CN=FABRIKAM-ADLDS1$instance1,CN=Servers,CN=Default-First-Site-Name,CN=Sites,CN=Configuration,CN={9131D98B-E210-480F-A95D-24F9396898CA}
subschemaSubentry             : CN=Aggregate,CN=Schema,CN=Configuration,CN={9131D98B-E210-480F-A95D-24F9396898CA}
supportedCapabilities         : {1.2.840.113556.1.4.1851 (LDAP_CAP_ACTIVE_DIRECTORY_ADAM_OID), 1.2.840.113556.1.4.1670 (LDAP_CAP_ACTIVE_DIRECTORY_V51_OID), 1.2.840.113556.1.4.1791 (LDAP_CAP_ACTIVE_DIRECTORY_LDAP_INTEG_OID), 1.2.840.113556.1.4.1935 (LDAP_CAP_ACTIVE_DIRECTORY_V61_OID)...}
supportedControl              : {1.2.840.113556.1.4.319 (LDAP_PAGED_RESULT_OID_STRING), 1.2.840.113556.1.4.801 (LDAP_SERVER_SD_FLAGS_OID), 1.2.840.113556.1.4.473 (LDAP_SERVER_SORT_OID), 1.2.840.113556.1.4.528 (LDAP_SERVER_NOTIFICATION_OID)...}
supportedLDAPPolicies         : {MaxPoolThreads, MaxDatagramRecv, MaxReceiveBuffer, InitRecvTimeout...}
supportedLDAPVersion          : {3, 2}
supportedSASLMechanisms       : {GSSAPI, GSS-SPNEGO, EXTERNAL, DIGEST-MD5}
```

This command gets the root of the directory server information tree of FABRIKAM-ADLDS1 using the FABRIKAM\user1 credentials.

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

- Fully qualified directory server name
- NetBIOS name
- Fully qualified directory server name and port

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

### None

## OUTPUTS

### Microsoft.ActiveDirectory.Management.ADRootDSE
An **ADRootDSE** object that represents the data tree for the specified directory server is output by this cmdlet.

## NOTES

## RELATED LINKS

