---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: ADFS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/adfs/new-adfsldapattributetoclaimmapping?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-AdfsLdapAttributeToClaimMapping
---

# New-AdfsLdapAttributeToClaimMapping

## SYNOPSIS
Creates a mapping between an attribute of an LDAP folder and an AD FS claim type.

## SYNTAX

```
New-AdfsLdapAttributeToClaimMapping [-LdapAttribute] <String> [[-ClaimType] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **New-AdfsLdapAttributeToClaimMapping** cmdlet creates a mapping between an attribute of the Lightweight Directory Access Protocol (LDAP) folder and an Active Directory Federation Services (AD FS) claim type.
Mappings make it possible for LDAP attributes to be available for claim rule processing in AD FS.

## EXAMPLES

### Example 1: Create a mapping of an LDAP directory attribute
```
PS C:\> $DisplayName = New-AdfsLdapAttributeToClaimMapping -LdapAttribute "displayName" -ClaimType "http://schemas.xmlsoap.org/ws/2005/05/identity/claims/displayname"
```

This command creates a mapping of an LDAP directory attribute to a claim type.
The command stores the mapping in the $DisplayName variable for use with other cmdlets.

To see this cmdlet as part of creating an LDAP local claims provider trust, see the **Add-AdfsLocalClaimsProviderTrust** cmdlet.

## PARAMETERS

### -ClaimType
Specifies the claim type to assign to the AD FS claim that contains the LDAP attribute value.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LdapAttribute
Specifies the attribute in the LDAP folder to which the claim type is mapped.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-AdfsLocalClaimsProviderTrust](./Add-AdfsLocalClaimsProviderTrust.md)

