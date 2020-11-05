---
external help file: WSBackup_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: E84ED988-6EFD-4B9B-BFD2-0C4A3D214BB0
manager: dansimp
---

# Get-WBSummary

## SYNOPSIS
Retrieves the history of backup operations on the computer.

## SYNTAX

```
Get-WBSummary
```

## DESCRIPTION
The **Get-WBSummary** cmdlet retrieves the history of backup operations on the computer.
This information includes the next scheduled backup, details of the last backup, and details of the last successful backup.
You can use this cmdlet to monitor the backups and the backup schedule on the computer.

To use this and any other Windows Server 2012 Backup cmdlets, you must be a member of the Administrators group or Backup Operators group.

## EXAMPLES

### Example 1: Get a backup summary
```
PS C:\> Get-WBSummary
```

This command gets information about the history of backups on the local computer.

## PARAMETERS

## INPUTS

### None
None

## OUTPUTS

### WBSummary
The Get-WBSummary cmdlet returns the **WBSummary** object that contains information about the backup history for this computer.

## NOTES

## RELATED LINKS

[Get-WBJob](./Get-WBJob.md)

[Start-WBBackup](./Start-WBBackup.md)

