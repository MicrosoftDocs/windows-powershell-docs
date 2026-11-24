---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Windows.DeveloperLicense.Commands.dll-Help.xml
Module Name: WindowsDeveloperLicense
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/windowsdeveloperlicense/get-windowsdeveloperlicense?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WindowsDeveloperLicense
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
For more information, see [Enable your device for development](https://msdn.microsoft.com/en-us/library/windows/apps/xaml/dn706236.aspx) (https://msdn.microsoft.com/en-us/library/windows/apps/xaml/dn706236.aspx) in the Microsoft Developer Network library.

## EXAMPLES

### Example 1: Check the status of Developer Mode DM
```
PS C:\> Get-WindowsDeveloperLicense
```

This command checks the status of Developer Mode for the current computer.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### WindowsDeveloperLicense

## NOTES

## RELATED LINKS

[Enable your device for development](https://msdn.microsoft.com/en-us/library/windows/apps/xaml/dn706236.aspx)

[Unregister-WindowsDeveloperLicense](./Unregister-WindowsDeveloperLicense.md)

[Show-WindowsDeveloperLicenseRegistration](./Show-WindowsDeveloperLicenseRegistration.md)

