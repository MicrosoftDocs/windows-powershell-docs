---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: brianlic
author: brianlic-msft
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
keywords: powershell, cmdlet
manager: alanth
ms.date: 12/20/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-AdfsWebConfig
ms.assetid: 130209C7-E07A-4926-B58B-E0AF7F027B32
---

# Get-AdfsWebConfig

## SYNOPSIS
Gets AD FS web customization configuration settings.

## SYNTAX

```
Get-AdfsWebConfig [<CommonParameters>]
```

## DESCRIPTION
The **Get-AdfsWebConfig** cmdlet gets Active Directory Federation Services (AD FS) web customization configuration settings.

## EXAMPLES

### Example 1: Get configuration settings
```
PS C:\> Get-AdfsWebConfig

ActiveThemeName      : Default
CDCCookieReader      :
CDCCookieWriter      :
HRDCookieLifetime    : 30
HRDCookieEnabled     : True
ContextCookieEnabled : True
```

This command gets the web customization configuration settings.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.IdentityServer.Management.Resources.AdfsWebConfig
This cmdlet generates an **AdfsWebConfig** object that represents AD FS web customization configuration settings.
This object contains the following properties: 

- ActiveThemeName: **System.String**
- CDCCookieReader: **System.Uri**
- CDCCookieWriter: **System.Uri**
- HRDCookieLifetime: **System.Int32**
- HRDCookieEnabled: **System.Boolean**
- ContextCookieEnabled: **System.Boolean**

## NOTES

## RELATED LINKS

[Set-AdfsWebConfig](./Set-AdfsWebConfig.md)

