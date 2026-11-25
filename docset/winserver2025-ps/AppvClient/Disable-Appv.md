---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.AppV.AppVClientPowerShell.dll-Help.xml
Module Name: AppvClient
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/appvclient/disable-appv?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-Appv
---

# Disable-Appv

## SYNOPSIS
Disables the App-V service.

## SYNTAX

```
Disable-Appv [<CommonParameters>]
```

## DESCRIPTION
The **Disable-Appv** cmdlet disables the Microsoft Application Virtualization (App-V) service on Windows 10 Anniversary Edition computers.
This cmdlet disables the download of all App-V apps from App-V Server or Configuration Manager.
If this cmdlet succeeds, it returns a message.
You must restart the computer for the change to take effect.

## EXAMPLES

### Example 1: Disable the App-V service
```
PS C:\> Disable-Appv
```

This command disables the App-V service.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Enable-Appv](./Enable-Appv.md)

[Get-AppvStatus](./Get-AppvStatus.md)

