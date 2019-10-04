---
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Windows.Appx.PackageManager.Commands.dll-help.xml
keywords: powershell, cmdlet
manager: jasgro
Module Name: Appx
ms.assetid: 658F6689-4A9E-4EF1-8C2F-F06BBD0947BD
ms.author: v-anbarr
ms.date: 12/20/2016
ms.mktglfcycl: manage
ms.prod: w10
ms.reviewer:
ms.sitesec: library
ms.technology: powershell-windows
ms.topic: reference
online version:
schema: 2.0.0
title: Get-AppxLastError
---

# Get-AppxLastError

## SYNOPSIS
Get the last error reported in the app package installation logs.

## SYNTAX

```
Get-AppxLastError [<CommonParameters>]
```

## DESCRIPTION
The **Get-AppxLastError** cmdlet gets the last error reported in the app package installation logs for the current Windows PowerShell® session.
An app package has an .appx file name extension.

## EXAMPLES

### Example 1: Get the last error
```
PS C:\> Get-AppxLastError
```

This command gets the last error reported in the app installation logs.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### System.Diagnostics.Eventing.Reader.EventLogRecord

## NOTES

## RELATED LINKS

[Package Manager API](http://go.microsoft.com/fwlink/?LinkId=245447)

[How to Deploy App Packages](http://go.microsoft.com/fwlink/?LinkID=231020)

[Get-AppxPackage](./Get-AppxPackage.md)

[Get-AppxPackageManifest](./Get-AppxPackageManifest.md)

[Get-AppxLog](./Get-AppxLog.md)

