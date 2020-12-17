---
author: Kateyanne
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
Module Name: ADFS
ms.assetid: 7F93BFE2-E432-4CE3-972D-57E2885C830F
ms.author: v-kaunu
ms.date: 12/20/2016
ms.mktglfcycl: manage
ms.prod: w10
ms.sitesec: library
ms.technology: 
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-AdfsTrustedFederationPartner
ms.reviewer:
---

# Get-AdfsTrustedFederationPartner

## SYNOPSIS
Gets a trusted federation partner in AD FS.

## SYNTAX

### Name (Default)
```
Get-AdfsTrustedFederationPartner [[-Name] <String[]>] [<CommonParameters>]
```

### FederationPartnerHostName
```
Get-AdfsTrustedFederationPartner [-FederationPartnerHostName] <Uri[]> [<CommonParameters>]
```

## DESCRIPTION
The **Get-AdfsTrustedFederationPartner** cmdlet gets federation partners that are trusted by this instance of Active Directory Federation Services (AD FS).

## EXAMPLES

## PARAMETERS

### -FederationPartnerHostName
Specifies an array of URIs of federation partners to get.

```yaml
Type: Uri[]
Parameter Sets: FederationPartnerHostName
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies an array of names of federation partners to get.

```yaml
Type: String[]
Parameter Sets: Name
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

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-AdfsTrustedFederationPartner](./Add-AdfsTrustedFederationPartner.md)

[Remove-AdfsTrustedFederationPartner](./Remove-AdfsTrustedFederationPartner.md)

[Set-AdfsTrustedFederationPartner](./Set-AdfsTrustedFederationPartner.md)

