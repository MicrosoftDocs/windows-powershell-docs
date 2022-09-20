---
external help file: WSBackup_Cmdlets.xml
Module Name: WindowsServerBackup
online version: https://learn.microsoft.com/powershell/module/windowsserverbackup/new-wbpolicy?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# New-WBPolicy

## SYNOPSIS
Creates a backup policy object.

## SYNTAX

```
New-WBPolicy
```

## DESCRIPTION
The **New-WBPolicy** cmdlet creates a backup policy object.
The new backup policy object does not contain information about the volumes included in the policy, the files in the backup, the backup target, or any scheduled times.

To make a new policy for scheduled backups, use the Set-WBPolicy cmdlet to define what items to include or exclude in backups, when to run backups, and where to store backups.
To make a one-time backup from policy settings, use the Start-WBBackup cmdlet.

To use this or any other Windows Server 2012 Backup cmdlet, you must be a member of the Administrators group or Backup Operators group.

## EXAMPLES

### Example 1: Create a backup policy
```
PS C:\> $Policy = New-WBPolicy
```

This command creates an empty **WBPolicy** object and saves it in the **$Policy** variable.
Use the **WBPolicy** object to specify the settings for backup.

## PARAMETERS

## INPUTS

### None
None

## OUTPUTS

### WBPolicy
The New-WBPolicy object generates an empty **WBPolicy** object in edit mode.

## NOTES

## RELATED LINKS

[Get-WBPolicy](./Get-WBPolicy.md)

[Remove-WBPolicy](./Remove-WBPolicy.md)

[Set-WBPolicy](./Set-WBPolicy.md)

[Start-WBBackup](./Start-WBBackup.md)

