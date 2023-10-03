---
external help file: WssCmdlets.dll-Help.xml
Module Name: WSSCmdlets
ms.date: 12/05/2017
online version: https://learn.microsoft.com/powershell/module/wsscmdlets/get-wssbackupjob?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WssBackupJob
---

# Get-WssBackupJob

## SYNOPSIS
Gets the status of current or previous backup jobs.

## SYNTAX

```
Get-WssBackupJob [[-JobCount] <UInt32>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-WssBackupJob** cmdlet gets the status of current or previous backup jobs.

## EXAMPLES

### Example 1: Get status past backup jobs
```
PS C:\> $ContosoBUJobs11 = Get-WssBackupJob -JobCount 10
```

This command gets the status of the previous 10 backup jobs and stores the status in the variable named $ContosoBUJobs11.

## PARAMETERS

### -JobCount
Specifies how many past backup jobs to retrieve.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.WindowsServerSolutions.DataProtection.ServerBackup.ObjectModel.BackupJob
This cmdlet returns the backup jobs retrieved.

## NOTES

## RELATED LINKS

[Start-WssBackupJob](./Start-WssBackupJob.md)

[Stop-WssBackupJob](./Stop-WssBackupJob.md)

