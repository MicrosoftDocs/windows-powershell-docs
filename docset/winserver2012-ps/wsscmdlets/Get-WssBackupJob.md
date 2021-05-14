---
external help file: WSS_Cmdlets.xml
Module Name: WssCmdlets
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/get-wssbackupjob?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-WssBackupJob

## SYNOPSIS
Gets the status of current or previous backup jobs.

## SYNTAX

```
Get-WssBackupJob [[-JobCount] <UInt32>]
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
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Start-WssBackupJob](./Start-WssBackupJob.md)

[Stop-WssBackupJob](./Stop-WssBackupJob.md)

