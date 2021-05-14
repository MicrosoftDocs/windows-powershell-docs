---
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
Module Name: ActiveDirectory
online version: https://docs.microsoft.com/powershell/module/activedirectory/set-addomainmode?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-ADDomainMode

## SYNOPSIS
Sets the domain mode for an Active Directory domain.

## SYNTAX

```
Set-ADDomainMode [-WhatIf] [-Confirm] [-AuthType <ADAuthType>] [-Credential <PSCredential>]
 [-DomainMode] <ADDomainMode> [-Identity] <ADDomain> [-PassThru] [-Server <String>] [<CommonParameters>]
```

## DESCRIPTION
The Set-ADDomainMode cmdlet sets the domain mode for a domain.
You specify the domain mode by setting the DomainMode parameter.

The domain mode can be set to the following values that are listed in order of functionality from lowest to highest.

Windows2000Domain

Windows2003InterimDomain

Windows2003Domain

Windows2008Domain

Windows2008R2Domain

You can change the domain mode to a mode with higher functionality only.
For example, if the domain mode for a domain is set to Windows 2003, you can use this cmdlet to change the mode to Windows 2008.
However, in the same situation, you cannot use this cmdlet to change the domain mode from Windows 2003 to Windows 2000.

The Identity parameter specifies the Active Directory domain to modify.
You can identify a domain by its distinguished name (DN), GUID, security identifier (SID), DNS domain name, or NetBIOS name.
You can also set the Identity parameter to a domain object variable such as $\<localADDomainObject\>, or you can pass a domain object through the pipeline to the Identity parameter.
For example, you can use the Get-ADDomain cmdlet to retrieve a domain object and then pass the object through the pipeline to the Set-ADDomainMode cmdlet.

The Set-ADDomainMode always prompts for permission unless you specify -confirm:$false.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
C:\PS>Set-ADDomainMode -Identity fabrikam.com -DomainMode Windows2003Domain
```

Description

-----------

Set the DomainMode property of the fabrikam.com domain to Windows2003Domain.

### -------------------------- EXAMPLE 2 --------------------------
```
C:\PS>$pdc = Get-ADDomainController -Discover -Service PrimaryDC
Set-ADDomainMode -Identity $pdc.Domain -Server $pdc.HostName[0] -DomainMode Windows2003Domain
```

Description

-----------

Set the DomainMode of the current logged on user's domain to Windows2003Domain.
The Set operation targets the PrimaryDC FSMO to apply the update.

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

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
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

### -DomainMode
Specifies the domain mode for an Active Directory domain.
You can set the domain mode to one of the following values that are listed in order of functionality from least to most.

Windows2000Domain or 0

Windows2003InterimDomain or 1

Windows2003Domain or 2

Windows2008Domain or 3

Windows2008R2Domain or 4

The following example shows how to set this parameter to Windows 2008 R2.

-DomainMode Windows2008R2Domain

```yaml
Type: ADDomainMode
Parameter Sets: (All)
Aliases: 
Accepted values: Windows2000Domain, Windows2003InterimDomain, Windows2003Domain, Windows2008Domain, Windows2008R2Domain, Windows2012Domain, UnknownDomain

Required: True
Position: 2
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
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -PassThru
Returns the new or modified object.
By default (i.e.
if -PassThru is not specified), this cmdlet does not generate any output.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
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

-By using the domain of the computer running Powershell.

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

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.ActiveDirectory.Management.ADDomain
A domain object is received by the Identity parameter.

## OUTPUTS

### None or Microsoft.ActiveDirectory.Management.ADDomain
Returns the modified domain object when the PassThru parameter is specified.
By default, this cmdlet does not generate any output.

## NOTES
* This cmdlet does not work with AD LDS.

  This cmdlet does not work with an Active Directory Snapshot.

  This cmdlet does not work with a read-only domain controller.

  This cmdlet does not work when connected to Global Catalog port.

## RELATED LINKS

[Get-ADDomain](./Get-ADDomain.md)

