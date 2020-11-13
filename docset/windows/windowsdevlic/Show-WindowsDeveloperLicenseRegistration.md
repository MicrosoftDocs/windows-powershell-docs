---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-kaunu
author: Kateyanne
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Windows.DeveloperLicense.Commands.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: 
ms.topic: reference
online version: 
schema: 2.0.0
title: Show-WindowsDeveloperLicenseRegistration
ms.reviewer:
ms.assetid: AF54274E-AB48-4A85-8839-CE11B5D6C2E3
---

# Show-WindowsDeveloperLicenseRegistration

## SYNOPSIS
Provides information about how to enable a device for development.

## SYNTAX

```
Show-WindowsDeveloperLicenseRegistration [<CommonParameters>]
```

## DESCRIPTION
The **Show-WindowsDeveloperLicenseRegistration** cmdlet opens a dialog box that explains how to enable your device for development in the Windows 10® operating system.
The dialog box provides a link to the new settings page.
For more information, see [Enable your device for development](https://msdn.microsoft.com/en-us/library/windows/apps/xaml/dn706236.aspx) (https://msdn.microsoft.com/en-us/library/windows/apps/xaml/dn706236.aspx) in the Microsoft Developer Network library.

You must have administrative credentials to enable Developer Mode.
You no longer need a Microsoft account or a developer license.

## EXAMPLES

### Example 1: Enable your device for development
```
PS C:\> Show-WindowsDeveloperLicenseRegistration
```

This command opens a dialog box that lets you enable your device for development.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Enable your device for development](https://msdn.microsoft.com/en-us/library/windows/apps/xaml/dn706236.aspx)

[Get-WindowsDeveloperLicense](./Get-WindowsDeveloperLicense.md)

[Unregister-WindowsDeveloperLicense](./Unregister-WindowsDeveloperLicense.md)

