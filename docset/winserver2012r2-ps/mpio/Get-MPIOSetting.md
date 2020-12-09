---
external help file: Mpio-help.xml
Module Name: MPIO
online version: 
schema: 2.0.0
title: Get-MPIOSetting
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 8B410DD8-9F6C-4077-A087-40771E19E468
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Get-MPIOSetting

## SYNOPSIS
Gets MPIO settings.

## SYNTAX

```
Get-MPIOSetting [<CommonParameters>]
```

## DESCRIPTION
The **Get-MPIOSetting** cmdlet gets Microsoft Multipath I/O (MPIO) settings.
The settings are as follows: 

- PathVerificationState
- PathVerificationPeriod
- PDORemovePeriod
- RetryCount
- RetryInterval
- UseCustomPathRecoveryTime
- CustomPathRecoveryTime
- DiskTimeoutValue

You can use the **Set-MPIOSetting** cmdlet to change these values.

## EXAMPLES

### Example 1: Get MPIO settings
```
PS C:\>Get-MPIOSetting
PathVerificationState     : Disabled

PathVerificationPeriod    : 30

PDORemovePeriod           : 20

RetryCount                : 3

RetryInterval             : 1

UseCustomPathRecoveryTime : Disabled

CustomPathRecoveryTime    : 40

DiskTimeoutValue          : 120
```

This command gets the MPIO settings.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Set-MPIOSetting](./Set-MPIOSetting.md)

