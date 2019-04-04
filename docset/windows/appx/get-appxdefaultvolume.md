---
author: kenwith
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Windows.Appx.PackageManager.Commands.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.assetid: 8D8598B3-D62C-4230-8D49-ECF24043ADA8
ms.author: kenwith
ms.date: 12/20/2016
ms.mktglfcycl: manage
ms.prod: w10
ms.sitesec: library
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-AppxDefaultVolume
ms.reviewer:
---

# Get-AppxDefaultVolume

## SYNOPSIS
Gets the default appx volume.

## SYNTAX

```
Get-AppxDefaultVolume [<CommonParameters>]
```

## DESCRIPTION
The **Get-AppxDefaultVolume** cmdlet gets the default **AppxVolume**.
The default **AppxVolume** is the default target for all deployment operations on the computer.
You cannot remove the default **AppxVolume** from the list of volumes.

## EXAMPLES

### Example 1: Get the default volume
```
PS C:\> Get-AppxDefaultVolume
```

This command gets the current default deployment target.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Appx.PackageManager.Commands.AppxVolume

## NOTES

## RELATED LINKS

[Set-AppxDefaultVolume](./Set-AppxDefaultVolume.md)
