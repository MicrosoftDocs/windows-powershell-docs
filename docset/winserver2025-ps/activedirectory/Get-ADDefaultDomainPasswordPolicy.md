---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
Module Name: ActiveDirectory
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/activedirectory/get-addefaultdomainpasswordpolicy?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ADDefaultDomainPasswordPolicy
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
The **Get-ADDefaultDomainPasswordPolicy** cmdlet gets the default password policy for a domain.

The *Identity* parameter specifies the Active Directory domain.
You can identify a domain by its distinguished name, GUID, Security Identifier (SID), DNS domain name, or NETBIOS name.
You can also set the parameter to a domain object variable, such as `$<localDomainObject>` or pass a domain object through the pipeline to the *Identity* parameter.

## EXAMPLES

### Example 1: Get the default domain password policy from the logged on user domain
```
PS C:\> Get-ADDefaultDomainPasswordPolicy -Current LoggedOnUser
```

This command gets the default domain password policy from current logged on user domain.

### Example 2: Get the default domain password policy from the current local computer
```
PS C:\> Get-ADDefaultDomainPasswordPolicy -Current LocalComputer
```

This command gets the default domain password policy from current local computer.

### Example 3: Get the default domain password policy from a specified domain
```
PS C:\> Get-ADDefaultDomainPasswordPolicy -Identity fabrikam.com
```

This command gets the default domain password policy from the domain specified by the **Site** parameter.

### Example 4: Get the default domain password policy objects from all the domains in the forest
```
PS C:\> (Get-ADForest -Current LoggedOnUser).Domains | %{ Get-ADDefaultDomainPasswordPolicy -Identity $_ }
```

This command gets the default domain password policy objects from all the domains in the forest.

### Example 5: Get the default domain password policy from the logged on user domain.
```
PS C:\> Get-ADDefaultDomainPasswordPolicy
```

This command gets the default domain password policy from current logged on user domain.

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
You can then set the Credential parameter to the **PSCredential** object.

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
- LoggedOnUser or 1

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
The identifier in parentheses is the Lightweight Directory Access Protocol (LDAP) display name for the attribute.
All values are for the domainDNS object that represents the domain.
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

### Microsoft.ActiveDirectory.Management.ADDomain
A domain object is received by the *Identity* parameter.

## OUTPUTS

### Microsoft.ActiveDirectory.Management.ADDefaultDomainPasswordPolicy
Returns the default domain password policy object for the specified domain.

## NOTES
* This cmdlet does not work with AD LDS.
* This cmdlet does not work when targeting a snapshot using the *Server* parameter.

## RELATED LINKS

[Set-ADDefaultDomainPasswordPolicy](./Set-ADDefaultDomainPasswordPolicy.md)

[Get-ADDomain](./Get-ADDomain.md)

[AD DS Administration Cmdlets in Windows PowerShell](./activedirectory.md)

