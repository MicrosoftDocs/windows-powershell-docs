---
external help file: WSS_Cmdlets.xml
Module Name: WssCmdlets
online version: https://learn.microsoft.com/powershell/module/wsscmdlets/get-wssglobalclientbackuppolicy?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-WssGlobalClientBackupPolicy

## SYNOPSIS
Gets the current global client backup policy.

## SYNTAX

```
Get-WssGlobalClientBackupPolicy
```

## DESCRIPTION
The **Get-WssGlobalClientBackupPolicy** cmdlet gets the current global client backup policy.
This policy includes the following values: 

- BackupStartTime.
The beginning of the backup window.
The default value is 18:00.
- BackupEndTime.
The end of the backup window.
The default value is 9:00.
- DailyRetainCount.
The number of daily backups to keep.
The default value is five. 
- WeeklyRetainCount.
The number of weekly backups to keep.
The default value is four.
- MonthlyRetainCount.
The number of monthly backups to keep.
The default value is six. 
- YearlyRetainCount.
The number of yearly backups to keep.
The default value is ten.

You can use the Set-WssGlobalClientBackupPolicy cmdlet to change any of these settings, or to reset all settings to their default values.

## EXAMPLES

### Example 1: Get the global client backup policy
```
PS C:\> Get-WssGlobalClientBackupPolicy
```

This command gets the global client backup policy.

## PARAMETERS

## INPUTS

### Microsoft.WindowsServerSolutions.DataProtection.PCBackup.BackupUtil.WcfContracts.PCBackupConfiguration

## OUTPUTS

## NOTES

## RELATED LINKS

[Set-WssGlobalClientBackupPolicy](./Set-WssGlobalClientBackupPolicy.md)

