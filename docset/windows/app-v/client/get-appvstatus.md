---
author: brianlic-msft
description: 
external help file: Microsoft.AppV.AppVClientPowerShell.dll-Help.xml
keywords: powershell, cmdlet
manager: alanth
ms.date: 2016-12-20
ms.prod: powershell
ms.technology: powershell
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-AppvStatus
ms.assetid: 7CA31DC5-62A4-4522-A065-BEDDC958BC6C
---

# Get-AppvStatus

## SYNOPSIS
Gets the status of the App-V service.

## SYNTAX

```
Get-AppvStatus [<CommonParameters>]
```

## DESCRIPTION
The **Get-AppvStatus** cmdlet gets the status of the Microsoft Application Virtualization (App-V) service.
This cmdlet returns a value of $True or $False for whether App-V is enabled and whether a restart is required.

## EXAMPLES

### Example 1: Get status
```
PS C:\>Get-AppvStatus
```

This command gets the status of the App-V service.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Disable-Appv](./Disable-Appv.md)

[Enable-Appv](./Enable-Appv.md)

