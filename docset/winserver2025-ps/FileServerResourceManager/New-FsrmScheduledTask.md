---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: FsrmScheduledTask.cdxml-help.xml
Module Name: FileServerResourceManager
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/fileserverresourcemanager/new-fsrmscheduledtask?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-FsrmScheduledTask
---

# New-FsrmScheduledTask

## SYNOPSIS
Creates a scheduled task object.

## SYNTAX

```
New-FsrmScheduledTask [-Time] <DateTime> [-RunDuration <Int32>] [-Weekly <FsrmScheduledTaskDaysEnum[]>]
 [-Monthly <Int32[]>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **New-FsrmScheduledTask** cmdlet creates a scheduled task object that defines scheduling for reports, classification, and file management jobs.

## EXAMPLES

### Example 1: Create a weekly scheduled task
```
PS C:\> $d = get-date "12:00am"
PS C:\> New-FsrmScheduledTask -Time $d -Weekly @(Monday, Tuesday, Wednesday, Thursday, Friday)
```

The first command gets a **DateTime** object and stores it in the variable $d.

The second command returns a **FsrmScheduledTask** object that defines a schedule that runs the task at midnight every day, Monday through Friday.

### Example 2: Create a monthly scheduled task
```
PS C:\> $d = get-date "12:00am"
PS C:\> New-FsrmScheduledTask -Time $d -Monthly @(-1,15) -RunDuration 4
```

The first command gets a **DateTime** object and stores it in the variable $d.

This second command returns a **FsrmScheduledTask** object that describes a schedule that runs the task at midnight on the 15th and the last day of every month.
The *RunDuration* parameter specifies that the server terminates the process after 4 hours if the process has not ended.

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to complete.

The cmdlet immediately returns an object that represents the job and then displays the command prompt.
You can continue to work in the session while the job completes.
To manage the job, use the `*-Job` cmdlets.
To get the job results, use the [Receive-Job](https://go.microsoft.com/fwlink/?LinkID=113372) cmdlet.

For more information about Windows PowerShell background jobs, see [about_Jobs](https://go.microsoft.com/fwlink/?LinkID=113251).

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: (All)
Aliases: Session

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Monthly
Specifies an array of days on which to run the task.
Specify a value of -1 to run the task on the last day of the month.
If you specify this parameter, do not specify the *Weekly* parameter.

```yaml
Type: Int32[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RunDuration
Specifies the number of hours that the server runs the task before canceling it.
The value 0 indicates that the server runs the task to completion.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ThrottleLimit
Specifies the maximum number of concurrent operations that can be established to run the cmdlet.
If this parameter is omitted or a value of `0` is entered, then Windows PowerShell® calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.
The throttle limit applies only to the current cmdlet, not to the session or to the computer.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Time
Specifies a date and time value, in standard Coordinated Universal Time (UTC) format, to run the task.

```yaml
Type: DateTime
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Weekly
Specifies an array of weekdays on which to run the task.
If you specify this parameter, do not specify the *Monthly* parameter.

```yaml
Type: FsrmScheduledTaskDaysEnum[]
Parameter Sets: (All)
Aliases:
Accepted values: Sunday, Monday, Tuesday, Wednesday, Thursday, Friday, Saturday

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.DateTime

### System.Int32

### Microsoft.PowerShell.Cmdletization.GeneratedTypes.FsrmScheduledTaskDaysEnum[]

### System.Int32[]

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance

## NOTES

## RELATED LINKS

[New-FsrmFileManagementJob](./New-FsrmFileManagementJob.md)

[New-FsrmStorageReport](./New-FsrmStorageReport.md)

[Set-FsrmClassification](./Set-FsrmClassification.md)

[Set-FsrmFileManagementJob](./Set-FsrmFileManagementJob.md)

[Set-FsrmStorageReport](./Set-FsrmStorageReport.md)

