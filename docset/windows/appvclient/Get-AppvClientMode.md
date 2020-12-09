---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-kaunu
author: Kateyanne
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.AppV.AppVClientPowerShell.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: 
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-AppvClientMode
ms.reviewer:
ms.assetid: 2AC1A44F-9F77-4B39-9417-3F9F59656F0F
---

# Get-AppvClientMode

## SYNOPSIS
Displays the mode for the App-V Client.

## SYNTAX

```
Get-AppvClientMode [<CommonParameters>]
```

## DESCRIPTION
The **Get-AppvClientMode** cmdlet displays the mode to which the Microsoft Application Virtualization (App-V) Client is currently.
The valid values are Normal and Uninstall.

## EXAMPLES


## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.AppV.AppvClientPowerShell.AppvClientMode
This cmdlet generates **AppvClientMode** object that describes the current App-V Client mode, either Normal or Uninstall.

## NOTES

## RELATED LINKS

[Set-AppvClientMode](./Set-AppvClientMode.md)

