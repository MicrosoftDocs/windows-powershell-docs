---
author: Kateyanne
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
manager: dansimp
Module Name: ActiveDirectory
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/activedirectory/get-addefaultdomainpasswordpolicy?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-ADDefaultDomainPasswordPolicy

## SYNOPSIS
Gets the default password policy for an Active Directory domain.

## SYNTAX

### Current (Default)
```
Get-ADDefaultDomainPasswordPolicy [-AuthType <ADAuthType>] [-Credential <PSCredential>]
 [[-Current] <ADCurrentDomainType>] [-Server <String>] [<CommonParameters>]
```

### Identity
```
Get-ADDefaultDomainPasswordPolicy [-AuthType <ADAuthType>] [-Credential <PSCredential>]
 [-Identity] <ADDefaultDomainPasswordPolicy> [-Server <String>] [<CommonParameters>]
```

## DESCRIPTION
The Get-ADDefaultDomainPasswordPolicy cmdlet gets the default password policy for a domain.

The Identity parameter specifies the Active Directory domain.
You can identify a domain by its Distinguished Name (DN), GUID, Security Identifier (SID), DNS domain name, or NETBIOS name.
You can also set the parameter to a domain object variable, such as $\<localDomainObject\> or pass a domain object through the pipeline to the Identity parameter.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
C:\PS>Get-ADDefaultDomainPasswordPolicy -Current LoggedOnUser
```

Description

-----------

Get the default domain password policy from current logged on user domain.

### -------------------------- EXAMPLE 2 --------------------------
```
C:\PS>Get-ADDefaultDomainPasswordPolicy -Current LocalComputer
```

Description

-----------

Get the default domain password policy from current local computer.

### -------------------------- EXAMPLE 3 --------------------------
```
C:\PS>Get-ADDefaultDomainPasswordPolicy -Identity fabrikam.com
```

Description

-----------

Get the default domain password policy from a given domain.

### -------------------------- EXAMPLE 4 --------------------------
```
C:\PS>(Get-ADForest -Current LoggedOnUser).Domains | %{ Get-ADDefaultDomainPasswordPolicy -Identity $_ }
```

Description

-----------

Get the default domain password policy objects from all the domains in the forest.

### -------------------------- EXAMPLE 5 --------------------------
```
C:\PS>Get-ADDefaultDomainPasswordPolicy
```

Description

-----------

Get the default domain password policy from current logged on user domain.

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
Position: 1
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
Type: ADDefaultDomainPasswordPolicy
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

### Microsoft.ActiveDirectory.Management.ADDomain
A domain object is received by the Identity parameter.

## OUTPUTS

### Microsoft.ActiveDirectory.Management.ADDefaultDomainPasswordPolicy
Returns the default domain password policy object for the specified domain.

## NOTES
* This cmdlet does not work with AD LDS.

  This cmdlet does not work when targeting a snapshot using the Server parameter.

## RELATED LINKS

[Get-ADDomain](./Get-ADDomain.md)

