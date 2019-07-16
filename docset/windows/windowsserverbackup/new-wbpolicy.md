---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-anbarr
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: wsbcmdlet.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/27/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: New-WBPolicy
ms.reviewer:
ms.assetid: DF2D77CE-FECB-45DE-A057-8BE4D9EBC1FE
---

# New-WBPolicy

## SYNOPSIS
Creates a backup policy object.

## SYNTAX

```
New-WBPolicy [<CommonParameters>]
```

## DESCRIPTION
The **New-WBPolicy** cmdlet creates a backup policy object.
The new backup policy object does not contain information about the volumes included in the policy, the files in the backup, the backup target, or any scheduled times.

To make a new policy for scheduled backups, use the [Set-WBPolicy](./Set-WBPolicy.md) cmdlet to define what items to include or exclude in backups, when to run backups, and where to store backups.
To make a one-time backup from policy settings, use the [Start-WBBackup](./Start-WBBackup.md) cmdlet.

To use this cmdlet, you must be a member of the Administrators group or Backup Operators group.

## EXAMPLES

### Example 1: Create a backup policy
```
PS C:\> $Policy = New-WBPolicy
```

This command creates an empty **WBPolicy** object and saves it in the $Policy variable.
Use the **WBPolicy** object to specify the settings for backup.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None
None

## OUTPUTS

### WBPolicy
This cmdlet returns and generates an empty **WBPolicy** object in edit mode.

## NOTES

## RELATED LINKS

[Get-WBPolicy](./Get-WBPolicy.md)

[Remove-WBPolicy](./Remove-WBPolicy.md)

[Set-WBPolicy](./Set-WBPolicy.md)

[Start-WBBackup](./Start-WBBackup.md)

