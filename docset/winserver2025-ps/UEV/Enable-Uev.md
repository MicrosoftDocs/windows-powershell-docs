---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Uev.Commands.dll-Help.xml
Module Name: UEV
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/uev/enable-uev?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-Uev
---

# Enable-Uev

## SYNOPSIS
Enables the UE-V service.

## SYNTAX

```
Enable-Uev [<CommonParameters>]
```

## DESCRIPTION
The **Enable-Uev** cmdlet enables the Microsoft User Experience Virtualization (UE-V) service on Windows 10 Anniversary edition computers.
This cmdlet enables synchronization of all UE-V settings.
The cmdlet returns a success message.

If you enable UE-V, you must restart the computer for the change to take effect.
Before you enable the UE-V service, configure UE-V service settings by using Windows PowerShell or Group Policy.

## EXAMPLES

### Example 1: Enable the UE-V service
```
PS C:\>Enable-Uev
```

This command enables the UE-V service.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Disable-Uev](./Disable-Uev.md)

[Get-UevStatus](./Get-UevStatus.md)

