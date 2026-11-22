---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: wsbcmdlet.dll-Help.xml
Module Name: WindowsServerBackup
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/windowsserverbackup/get-wbsummary?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WBSummary
---

# Get-WBSummary

## SYNOPSIS
Gets the history of backup operations on the computer.

## SYNTAX

```
Get-WBSummary [<CommonParameters>]
```

## DESCRIPTION
The **Get-WBSummary** cmdlet gets the history of backup operations on the computer.
This information includes the next scheduled backup, details of the last backup, and details of the last successful backup.
You can use this cmdlet to monitor the backups and the backup schedule on the computer.

To use this cmdlet, you must be a member of the Administrators group or Backup Operators group.

## EXAMPLES

### Example 1: Get a backup summary
```
PS C:\> Get-WBSummary
```

This command gets information about the history of backups on the local computer.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Get-WBJob](./Get-WBJob.md)

[Start-WBBackup](./Start-WBBackup.md)

