---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: DedupSchedule.cdxml-help.xml
Module Name: Deduplication
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/deduplication/new-dedupschedule?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-DedupSchedule
---

# New-DedupSchedule

## SYNOPSIS
Creates a data deduplication schedule.

## SYNTAX

```
New-DedupSchedule [-Name] <String> [-Type] <Type> [-DurationHours <UInt32>] [-Disable]
 [-StopWhenSystemBusy] [-Memory <UInt32>] [-Cores <UInt32>] [-Priority <Priority>]
 [-InputOutputThrottle <UInt32>] [-InputOutputThrottleLevel <InputOutputThrottleLevel>]
 [-Start <DateTime>] [-Days <DayOfWeek[]>] [-Full] [-ReadOnly]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION

The `New-DedupSchedule` cmdlet creates a data deduplication schedule. This cmdlet returns a
**DeduplicationSchedule** object that you can use to customize the data deduplication schedule. This
cmdlet uses default settings to create a data deduplication schedule for the parameters that you do
not specify.

You can create a schedule to run the following types data deduplication jobs:

- `Optimization` This job performs both deduplication and compression of files according data
  deduplication policy for the volume. After initial optimization of a file, if that file is then
  modified and again meets the data deduplication policy threshold for optimization, the file is
  optimized again.
- `GarbageCollection` This job processes deleted or modified data on the volume so that any data
  chunks that are no longer referenced are cleaned up. Garbage collection jobs process previously
  deleted or logically overwritten optimized content to create usable volume free space. When an
  optimized file is deleted or overwritten by new data, the old data in the chunk store is not
  immediately deleted. Garbage collection is scheduled to run weekly by default. Garbage collection
  is a processing-intensive operation, so you should allow the deletion load to reach a threshold
  and then manually run this job type, or schedule it for off hours.
- `Scrubbing` This job processes data corruptions it finds during data integrity validation,
  performs possible corruption repair, and generates a scrubbing report.
- `Unoptimization` This job undoes data deduplication on all of the optimized files on the volume.
  At the end of a successful unoptimization job, the server deletes all of the data deduplication
  metadata from the volume.

For more information, see
[Install and Configure Data Deduplication](https://technet.microsoft.com/library/hh831434.aspx) on
TechNet.

## EXAMPLES

### Example 1: Create a data deduplication schedule for a garbage collection job

```powershell
$params = @{
    Days          = 'Sunday'
    DurationHours = 5
    Name          = 'OffHoursGC'
    Priority      = 'Normal'
    Start         = '08:00'
    Type          = 'GarbageCollection'
}
New-DedupSchedule @params
```

This command creates a data deduplication schedule with a **Name** of `OffHoursGC`. The
deduplication job **Type** is `GarbageCollection`. The job is scheduled to run every `Sunday` via
the **Days** Parameter. The job will **Start** at `08:00` and run at `Normal` **Priority**. The
command specifies **DurationHours** of `5` causing the server to cancel the job after 5 hours if the
process has not ended.

### Example 2: Create a data deduplication schedule for a scrubbing job

```powershell
$params = @{
    Days               = @(
        'Monday'
        'Tuesday'
        'Wednesday'
        'Thursday'
        'Friday'
    )
    DurationHours      = 6
    Name               = 'OffHoursScrub'
    Priority           = 'Normal'
    Start              = '23:00'
    StopWhenSystemBusy = $true
    Type               = 'Scrubbing'
}
New-DedupSchedule @params
```

This command creates a data deduplication schedule for a `Scrubbing` **Type** job named
`OffHoursScrub`. The command starts the scrubbing job at `23:00` on each day Monday through Friday.
The **StopWhenSystemBusy** parameter specifies that the server stops the job when the system is busy
and retries later. The **DurationHours** parameter specifies that the server cancels the job after
`6` hours if the process has not ended. The job will run at `Normal` **Priority**

### Example 3: Create a data deduplication schedule for an optimization job

```powershell
$params = @{
    Days          = @(
        'Mon'
        'Tues'
        'Wed'
        'Thurs'
        'Fri'
    )
    DurationHours = 9
    Name          = 'MyWeekdayOptimization'
    Start         = '08:00'
    Type          = 'Optimization'
}
New-DedupSchedule @params
```

This command creates a data deduplication schedule for an `Optimization` **Type** job named
`MyWeekdayOptimization`. The optimization job runs at a normal **Priority** every weekday evening at
`08:00`. The **DurationHours** parameter specifies that the server cancels the job after `9` hours
if the process has not ended.

## PARAMETERS

### -AsJob

Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to
complete.

The cmdlet immediately returns an object that represents the job and then displays the command
prompt. You can continue to work in the session while the job completes. To manage the job, use the
`*-Job` cmdlets. To get the job results, use the
[Receive-Job](https://go.microsoft.com/fwlink/?LinkID=113372) cmdlet.

For more information about Windows PowerShell background jobs, see
[about_Jobs](https://go.microsoft.com/fwlink/?LinkID=113251).

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CimSession

Runs the cmdlet in a remote session or on a remote computer. Enter a computer name or a session
object, such as the output of a [New-CimSession](/powershell/module/cimcmdlets/new-cimsession) or
[Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet. The default is the
current session on the local computer.

```yaml
Type: Microsoft.Management.Infrastructure.CimSession[]
Parameter Sets: (All)
Aliases: Session

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Cores

Specifies an array of maximum percentages of physical cores that a job uses.

```yaml
Type: System.UInt32
Parameter Sets: (All)
Aliases: MaximumCoresPercentage

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Days

Specifies an array of days of the week on which the server runs the data deduplication job. The
acceptable values for this parameter are:

- `Monday`
- `Tuesday`
- `Wednesday`
- `Thursday`
- `Friday`
- `Saturday`
- `Sunday`

```yaml
Type: System.DayOfWeek[]
Parameter Sets: (All)
Aliases:
Accepted values: Sunday, Monday, Tuesday, Wednesday, Thursday, Friday, Saturday

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Disable

Indicates that the server disables the data deduplication schedule immediately after you create it.
The server does not run the data deduplication schedule at the time that you specify in the
**Start** parameter. After you disable a data deduplication schedule, you can use the
**Set-DedupSchedule** cmdlet to enable the schedule.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DurationHours

Specifies the number of hours that the server runs the task before canceling it. The value `0`
indicates that the server runs the job to completion. This cmdlet safely stops a data deduplication
job and does not affect the files that the server is processing when it cancels the job.

```yaml
Type: System.UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Full

Indicates that garbage collection jobs free up all deleted or unreferenced data on the volume, if
you specify the value `GarbageCollection` for the **Type** parameter. If you do not specify this
parameter, garbage collection jobs free up space after a system threshold of delete data is
exceeded. We recommend that you run garbage collection regularly without specifying this parameter,
and then once a month specify this parameter and run garbage collection again.

If you specify the value `Scrubbing` for the **Type** parameter, this parameter indicates that
scrubbing jobs validate the integrity of all data on the volume. If you do not specify this
parameter, the scrubbing job validates only critical metadata and data integrity issues that data
deduplication previously encountered. We recommend that you run scrubbing regularly without
specifying this parameter, and then once a month specify this parameter and run scrubbing again.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InputOutputThrottle

Specifies the amount of input/output throttling applied to the deduplication job. Throttling ensures
that deduplication does not interfere with other I/O intensive processes. The acceptable values for
this parameter are: integers from 0 to 100. If you specify this parameter and the
**InputOutputThrottleLevel** parameter, **InputOutputThrottle** takes precedence.

```yaml
Type: System.UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputOutputThrottleLevel

Specifies the amount of I/O throttling that the job provides to ensure that the job does not
interfere with other I/O intensive processes. The acceptable values for this parameter are:

- `None`
- `Low`
- `Medium`
- `High`

```yaml
Type: InputOutputThrottleLevel
Parameter Sets: (All)
Aliases:
Accepted values: None, Low, Medium, High, Maximum

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Memory

Specifies the maximum percentage of physical computer memory that the data deduplication job can
use.

For optimization jobs, we recommend that you set a range from `15` to `50`, and a higher memory
consumption for jobs that you schedule to run when you specify the **StopWhenSystemBusy** parameter.
For garbage collection and scrubbing jobs, which you typically schedule to run in off hours, you can
set a higher memory consumption, such as `50`.

```yaml
Type: System.UInt32
Parameter Sets: (All)
Aliases: MaximumMemoryPercentage

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name

Specifies a name for the data deduplication job schedule.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Priority

Sets the CPU and I/O priority for the optimization job that you run by using this cmdlet. For jobs
that you run when you specify the **StopWhenSystemBusy** parameter, we recommend that you set this
parameter to `Low`. For typical optimization jobs, we recommend that you set this parameter to
`Normal`.

```yaml
Type: Priority
Parameter Sets: (All)
Aliases:
Accepted values: Low, Normal, High

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ReadOnly

Indicates that the scrubbing job processes and reports on corruptions that it finds but does not run
any repair actions.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Start

Specifies a time to start this job. The default value is 1:45am.
Type the date in a format that is standard for the system locale, such as `dd-MM-yyyy` (German
\[Germany\]) or `MM/dd/yyyy` (English \[United States\]).

```yaml
Type: System.DateTime
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StopWhenSystemBusy

Indicates that the server stops the job when the system is busy and retries later. We recommend that
you specify this parameter when you set a low priority for the job.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ThrottleLimit

Specifies the maximum number of concurrent operations that can be established to run the cmdlet. If
this parameter is omitted or a value of `0` is entered, then Windows PowerShell® calculates an
optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the
computer. The throttle limit applies only to the current cmdlet, not to the session or to the
computer.

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

### -Type

Specifies the type of data deduplication job. The acceptable values for this parameter are:

- `Optimization`
- `GarbageCollection`
- `Scrubbing`
- `Unoptimization`

```yaml
Type: Type
Parameter Sets: (All)
Aliases:
Accepted values: Optimization, GarbageCollection, Scrubbing, Unoptimization

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.DateTime

### System.DayOfWeek[]

### System.Management.Automation.SwitchParameter

### System.UInt32

### Microsoft.PowerShell.Cmdletization.GeneratedTypes.DedupSchedule.Priority

### Microsoft.PowerShell.Cmdletization.GeneratedTypes.DedupSchedule.Type

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance

The **Microsoft.Management.Infrastructure.CimInstance** object is a wrapper class that displays
Windows Management Instrumentation (WMI) objects. The path after the pound sign (`#`) provides the
namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Get-DedupSchedule](./Get-DedupSchedule.md)

[Remove-DedupSchedule](./Remove-DedupSchedule.md)

[Set-DedupSchedule](./Set-DedupSchedule.md)
