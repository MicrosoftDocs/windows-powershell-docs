---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: ADFS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/adfs/get-adfsauthenticationprovider?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-AdfsAuthenticationProvider
---

# Get-AdfsAuthenticationProvider

## SYNOPSIS
Gets a list of all authentication providers in AD FS.

## SYNTAX

```
Get-AdfsAuthenticationProvider [[-Name] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AdfsAuthenticationProvider** cmdlet gets a list of all authentication providers currently registered in Active Directory Federation Services (AD FS).
The read-only list includes built-in and external authentication providers and associated properties.

## EXAMPLES

### Example 1: Get all registered authentication providers
```
PS C:\> Get-AdfsAuthenticationProvider
AdminName                          : Forms Authentication
AllowedForPrimaryExtranet          : True
AllowedForPrimaryIntranet          : True
AllowedForAdditionalAuthentication : False
AuthenticationMethods              : {urn:oasis:names:tc:SAML:1.0:am:password, urn:oasis:names:tc:SAML:2.0:ac:classes:Password, urn:oasis:names:tc:SAML:2.0:ac:classes:PasswordProtectedTransport, http://schemas.microsoft.com/ws/2008/06/identity/authenticationmethod/password}
Descriptions                       : {}
DisplayNames                       : {}
Name                               : FormsAuthentication
IdentityClaims                     : {}
IsCustom                           : False
RequiresIdentity                   : False

AdminName                          : Windows Authentication
AllowedForPrimaryExtranet          : False
AllowedForPrimaryIntranet          : True
AllowedForAdditionalAuthentication : False
AuthenticationMethods              : {urn:ietf:rfc:1510, urn:federation:authentication:windows, urn:oasis:names:tc:SAML:2.0:ac:classes:Kerberos, http://schemas.microsoft.com/ws/2008/06/identity/authenticationmethod/kerberos...} Descriptions                       : {}
DisplayNames                       : {}
Name                               : WindowsAuthentication
IdentityClaims                     : {}
IsCustom                           : False
RequiresIdentity                   : False

AdminName                          : Certificate Authentication
AllowedForPrimaryExtranet          : True
AllowedForPrimaryIntranet          : True
AllowedForAdditionalAuthentication : True
AuthenticationMethods              : {urn:ietf:rfc:2246, urn:oasis:names:tc:SAML:1.0:am:X509-PKI, urn:oasis:names:tc:SAML:2.0:ac:classes:TLSClient, urn:oasis:names:tc:SAML:2.0:ac:classes:X509...} Descriptions                       : {}
DisplayNames                       : {}
Name                               : CertificateAuthentication
IdentityClaims                     : {}
IsCustom                           : False
RequiresIdentity                   : False
```

This command gets all authentication providers currently registered in AD FS.

## PARAMETERS

### -Name
Specifies the name of an authentication provider to retrieve from AD FS.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Register-AdfsAuthenticationProvider](./Register-AdfsAuthenticationProvider.md)

[Unregister-AdfsAuthenticationProvider](./Unregister-AdfsAuthenticationProvider.md)

