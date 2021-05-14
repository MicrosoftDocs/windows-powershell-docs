---
external help file: WSBackup_Cmdlets.xml
Module Name: WindowsServerBackup
online version: https://docs.microsoft.com/powershell/module/windowsserverbackup/get-wbsummary?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
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

