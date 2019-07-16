---
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
Module Name: ADFS
ms.assetid: EAE924E8-5BC3-4D00-9ED0-96FB35B96420
ms.author: v-anbarr
ms.date: 12/20/2016
ms.mktglfcycl: manage
ms.prod: w10
ms.sitesec: library
ms.technology: powershell-windows
ms.topic: reference
online version:
schema: 2.0.0
title: Get-AdfsApplicationPermission
ms.reviewer:
---

# Get-AdfsApplicationPermission

## SYNOPSIS
Gets permission for an application.

## SYNTAX

### Identifier (Default)
```
Get-AdfsApplicationPermission [[-Identifiers] <String[]>] [<CommonParameters>]
```

### ClientRoleIdentifier
```
Get-AdfsApplicationPermission [[-ClientRoleIdentifiers] <String[]>] [<CommonParameters>]
```

### ServerRoleIdentifier
```
Get-AdfsApplicationPermission [[-ServerRoleIdentifiers] <String[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AdfsApplicationPermission** cmdlet gets permission for an application in Active Directory Federation Services (AD FS).

## EXAMPLES

## PARAMETERS

### -ClientRoleIdentifiers
Specifies an array of client role identifiers.

```yaml
Type: String[]
Parameter Sets: ClientRoleIdentifier
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Identifiers
Specifies an array of identifiers.

```yaml
Type: String[]
Parameter Sets: Identifier
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ServerRoleIdentifiers
Specifies an array of server role identifiers.

```yaml
Type: String[]
Parameter Sets: ServerRoleIdentifier
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String[]

## OUTPUTS

### Microsoft.IdentityServer.Management.Resources.OAuthPermission
ClientRoleIdentifier  string
ConsentType           Microsoft.IdentityServer.Protocols.PolicyStore.OAuthConsentType
Description           string
GrantedAt             datetime
GrantedBy             string
ObjectIdentifier      string
ScopeNames            string[]
ServerRoleIdentifier  string

### Microsoft.IdentityServer.Protocols.PolicyStore.OAuthConsentType

OAuthConsentType
{
  Unknown = 0,
  Administrator = 1,
  User = 2,
}

## NOTES

## RELATED LINKS

[Grant-AdfsApplicationPermission](./Grant-AdfsApplicationPermission.md)

[Revoke-AdfsApplicationPermission](./Revoke-AdfsApplicationPermission.md)

[Set-AdfsApplicationPermission](./Set-AdfsApplicationPermission.md)
