---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Windows.Appx.PackageManager.Commands.dll-Help.xml
Module Name: Appx
ms.date: 05/15/2023
online version: https://learn.microsoft.com/powershell/module/appx/get-appxdefaultvolume?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-AppxDefaultVolume
---

# Get-AppxDefaultVolume

## SYNOPSIS
Gets the default appx volume.

## SYNTAX

```
Get-AppxDefaultVolume [<CommonParameters>]
```

## DESCRIPTION

The `Get-AppxDefaultVolume` cmdlet gets the default **AppxVolume**. The default **AppxVolume** is
the default target for all deployment operations on the computer. You can't remove the default
**AppxVolume** from the list of volumes.

## EXAMPLES

### Example 1: Get the default volume

```powershell
Get-AppxDefaultVolume
```

This command gets the current default deployment target.

## PARAMETERS

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Appx.PackageManager.Commands.AppxVolume

## NOTES

## RELATED LINKS

[Set-AppxDefaultVolume](./Set-AppxDefaultVolume.md)
