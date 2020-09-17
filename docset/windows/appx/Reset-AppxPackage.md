---
author: rdmaclachlan
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Windows.Appx.PackageManager.Commands.dll-help.xml
keywords: powershell, cmdlet
manager: jvintzel
Module Name: Appx
ms.assetid: 40B54C64-C3EB-4898-AE19-CDD5CA3BD70E
ms.author: romaclac
ms.date: 08/06/2020
ms.mktglfcycl: manage
ms.prod: w10
ms.reviewer:
ms.sitesec: library
ms.technology: powershell-windows
ms.topic: reference
online version:
schema: 2.0.0
title: Reset-AppxPackage
---

# Reset-AppxPackage

Starting at Windows 10 Insider Preview Build 20215 you get access to the `Rest-AppxPackage` PowerShell Cmdlet for use in resetting your installed Windows Apps.

## SYNOPSIS

Restores the Windows app to its initial configuration.

## SYNTAX

```PowerShell
Reset-AppxPackage [-Package] <string>
                  [-WhatIf] 
                  [-Confirm] 
                  [<CommonParameters>]
```

## DESCRIPTION


## EXAMPLES

### Example 1: Reset app package
```
PS C:\> Reset-AppxPackage -Package publisher.package1_1.0.0.0_neutral__8wekyb3d8bbwe
```

This cmdlet will reset the `publisher.package1_1.0.0.0_neutral__8wekyb3d8bbwe` application back to its original settings.

## PARAMETERS

### -Package
Specifies the full package name which will be reset

```yaml
Type: String[]
Parameter Sets: None
Aliases: None

Required: True
Position: Named
Default value: None
Accept pipeline input: True
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String[]

### System.IO.FileInfo

## OUTPUTS

### None

## NOTES

## RELATED LINKS

