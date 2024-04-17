---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.AppV.AppVClientPowerShell.dll-Help.xml
Module Name: AppvClient
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/appvclient/get-appvstatus?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-AppvStatus
---

# Get-AppvStatus

## SYNOPSIS
Gets the status of the App-V service.

## SYNTAX

```
Get-AppvStatus [<CommonParameters>]
```

## DESCRIPTION
The **Get-AppvStatus** cmdlet gets the status of the Microsoft Application Virtualization (App-V) service.
This cmdlet returns a value of $True or $False for whether App-V is enabled and whether a restart is required.

## EXAMPLES

### Example 1: Get status
```
PS C:\> Get-AppvStatus
```

This command gets the status of the App-V service.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Disable-Appv](./Disable-Appv.md)

[Enable-Appv](./Enable-Appv.md)

