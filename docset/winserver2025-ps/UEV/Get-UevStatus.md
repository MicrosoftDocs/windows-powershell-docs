---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Uev.Commands.dll-Help.xml
Module Name: UEV
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/uev/get-uevstatus?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-UevStatus
---

# Get-UevStatus

## SYNOPSIS
Gets the status of the UE-V service.

## SYNTAX

```
Get-UevStatus [<CommonParameters>]
```

## DESCRIPTION
The **Get-UevStatus** cmdlet gets the status of the Microsoft User Experience Virtualization (UE-V) service.
This cmdlet returns whether UE-V is enabled and whether a restart is required.

## EXAMPLES

### Example 1: Get status of the UE-V service
```
PS C:\>Get-UevStatus
```

This command gets the status of the UE-V service.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Disable-Uev](./Disable-Uev.md)

[Enable-Uev](./Enable-Uev.md)

