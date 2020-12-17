---
external help file: Microsoft.Windows.Appx.PackageManager.Commands.dll-help.xml
Module Name: Appx
online version: 
schema: 2.0.0
title: Get-AppxLastError
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/29/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 658F6689-4A9E-4EF1-8C2F-F06BBD0947BD
---

# Get-AppxLastError

## SYNOPSIS
Get the last error reported in the app package installation logs.

## SYNTAX

```
Get-AppxLastError [<CommonParameters>]
```

## DESCRIPTION
The **Get-AppxLastError** function gets the last error reported in the app package (.appx) installation logs for the current Windows PowerShell session.

## EXAMPLES

### Example 1
```
PS C:\>Get-AppxLastError
```

This example gets the last error reported in the app installation logs.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### System.Diagnostics.Eventing.Reader.EventLogRecord

## NOTES

## RELATED LINKS

[Package Manager API](https://go.microsoft.com/fwlink/?LinkId=245447)

[How to Deploy App Packages](https://go.microsoft.com/fwlink/?LinkID=231020)

[Get-AppxPackage](./Get-AppxPackage.md)

[Get-AppxPackageManifest](./Get-AppxPackageManifest.md)

[Remove-AppxPackage](./Remove-AppxPackage.md)

[Get-AppxLog](./Get-AppxLog.md)

[Add-AppxPackage](./Add-AppxPackage.md)

