---
author: brianlic
description: 
external help file: Microsoft.Windows.KpsServer.Administration.dll-Help.xml
keywords: powershell, cmdlet
manager: alanth
ms.date: 2016-12-20
ms.prod: powershell
ms.technology: powershell
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-HgsKeyProtectionConfiguration
ms.assetid: 6084E3ED-408C-492B-8294-C12ABFC1F7C3
---

# Get-HgsKeyProtectionConfiguration

## SYNOPSIS
Gets the configuration of the Key Protection Service.

## SYNTAX

```
Get-HgsKeyProtectionConfiguration [<CommonParameters>]
```

## DESCRIPTION
The **Get-HgsKeyProtectionConfiguration** cmdlet gets the configuration of the Key Protection Service that runs on the local computer.
The configuration contains the communication certificate that the Key Protection Service uses to sign the metadata provided by the service.

## EXAMPLES

### Example 1: Get the configuration of the Key Protection Service
```
PS C:\>Get-HgsKeyProtectionConfiguration
```

This command gets the configuration of the Key Protection Service on the local computer.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None
You cannot pipe input to this cmdlet.

## OUTPUTS

### Microsoft.Windows.KpsServer.Common.Store.Data.ServiceConfiguration
This cmdlet returns the configuration of Key Protection Service set up on the local computer.

## NOTES

## RELATED LINKS

[Set-HgsKeyProtectionConfiguration](./Set-HgsKeyProtectionConfiguration.md)

