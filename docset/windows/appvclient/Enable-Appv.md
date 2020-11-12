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
title: Enable-Appv
ms.reviewer:
ms.assetid: 6BF54948-0212-42EC-8704-754AD93EB2B7
---

# Enable-Appv

## SYNOPSIS
Enables the App-V service.

## SYNTAX

```
Enable-Appv [<CommonParameters>]
```

## DESCRIPTION
The **Enable-Appv** cmdlet enables the Microsoft Application Virtualization (App-V) service on computers running at least Windows 10 Anniversary Edition (version 1607) .
If this cmdlet succeeds, it returns a message.

Before you enable the App-V service, configure App-V service settings by using Windows PowerShell or Group Policy.

## EXAMPLES

### Example 1: Enable the service
```
PS C:\> Enable-Appv
```

This command enables the App-V service.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Disable-Appv](./Disable-Appv.md)

[Get-AppvStatus](./Get-AppvStatus.md)

