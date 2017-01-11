---
author: brianlic-msft
description: 
external help file: Microsoft.Windows.DeveloperLicense.Commands.dll-Help.xml
keywords: powershell, cmdlet
manager: alanth
ms.date: 2016-12-20
ms.prod: powershell
ms.technology: powershell
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-WindowsDeveloperLicense
ms.assetid: 73687EB6-DAF8-4003-BDB3-5599E543F67E
---

# Get-WindowsDeveloperLicense

## SYNOPSIS
Provides information about Developer Mode for the current computer.

## SYNTAX

```
Get-WindowsDeveloperLicense [<CommonParameters>]
```

## DESCRIPTION
The **Get-WindowsDeveloperLicense** cmdlet provides information about whether you enabled Developer Mode for the current computer.
You no longer need a developer license.
Therefore, there is no longer an expiration date for a developer license.
For more information, see Enable your device for developmenthttps://msdn.microsoft.com/en-us/library/windows/apps/xaml/dn706236.aspx (https://msdn.microsoft.com/en-us/library/windows/apps/xaml/dn706236.aspx) in the Microsoft Developer Network library.

## EXAMPLES

### Example 1: Check the status of Ddeveloper Mmode DM
```
PS C:\> Get-WindowsDeveloperLicense
```

This command checks the status of Developer Mode for the current computer.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### WindowsDeveloperLicense

## NOTES

## RELATED LINKS

[Enable your device for development](https://msdn.microsoft.com/en-us/library/windows/apps/xaml/dn706236.aspx)

[Unregister-WindowsDeveloperLicense](./Unregister-WindowsDeveloperLicense.md)

[Show-WindowsDeveloperLicenseRegistration](./Show-WindowsDeveloperLicenseRegistration.md)

