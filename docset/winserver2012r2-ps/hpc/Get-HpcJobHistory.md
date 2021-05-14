---
Module Name: HPC
ms.date: 12/20/2016
online version: https://docs.microsoft.com/powershell/module/hpc/get-hpcjobhistory?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-HpcJobHistory
---

# Get-HpcJobHistory

## SYNOPSIS
Gets the job history data for all finished, canceled, and failed jobs.

## SYNTAX

```
Get-HpcJobHistory [-StartDate] <DateTime> [-EndDate] <DateTime> [-Scheduler <String[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-HpcJobHistory** cmdlet gets the job history data for all finished, canceled, and failed jobs for the specified time period.
You can export this information to a database and create and run reports on the information.
The time period is on and after the specified start date and time and before the specified end date and time.

You can schedule this cmdlet to run daily and export the job history to a database.
You can then use this database to track job history.

## EXAMPLES

### Example 1: Get job history for the prior day
```
PS C:\>Get-HpcJobHistory -StartDate (Get-Date).AddDays(-1) -EndDate (Get-Date)
```

This command gets the job history for the past day.
Run this cmdlet daily at midnight or some other appropriate time to update the database that you use to track job history.

### Example 2: Get job history for multiple days
```
PS C:\>Get-HpcJobHistory -StartDate "7/12/2008 12:00:00 AM" -EndDate "7/23/2008 12:00:00 AM"
```

This command gets the job history for the period on and after 7/12/2008 and before 7/23/2008.

## PARAMETERS

### -EndDate
Specifies a **DateTime** object or a date string that is compatible with the current date format on your computer for the end date and time for the time period for which you want to retrieve the job history.
Use the Get-Date cmdlet to get a **DateTime** object for a date and time.

```yaml
Type: DateTime
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Scheduler
Specifies the host name or IP address of the head node for the cluster on which ran the jobs for which you want to get history data.
The value must be a valid computer name or IP address.
If you do not specify the *Scheduler* parameter, this cmdlet uses the scheduler on the head node that the CCP_SCHEDULER environment variable specifies.
To set this environment variable, run the following cmdlet:

`Set-Content Env:CCP_SCHEDULER \<head_node_name\>`

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StartDate
Specifies a **DateTime** object or a date string that is compatible with the current date format on your computer for the start date and time for the time period for which you want to retrieve the job history.
Use the Get-Date cmdlet to get a **DateTime** object for a date and time.

```yaml
Type: DateTime
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### HpcJobHistory[]

## NOTES
* You must be a cluster administrator to run this cmdlet successfully.

## RELATED LINKS

[Get-HpcNodeStateHistory](./Get-HpcNodeStateHistory.md)
