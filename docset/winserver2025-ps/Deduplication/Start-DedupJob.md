---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: DedupJob.cdxml-help.xml
Module Name: Deduplication
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/deduplication/start-dedupjob?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Start-DedupJob
---

# Start-DedupJob

## SYNOPSIS
Starts a data deduplication job.

## SYNTAX

```
Start-DedupJob [-Type] <Type> [[-Volume] <String[]>] [-StopWhenSystemBusy]
 [-Memory <UInt32>] [-Cores <UInt32>] [-Priority <Priority>]
 [-InputOutputThrottle <UInt32>] [-InputOutputThrottleLevel <InputOutputThrottleLevel>]
 [-Preempt] [-Wait] [-Full] [-ReadOnly] [-Timestamp <DateTime>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION

The `Start-DedupJob` starts a new data deduplication job for one or more volumes. The data
deduplication job can queue if the server is running another job on the same volume or if the
computer does not have sufficient resources to run the job. The server marks the queued jobs that
you start with this cmdlet as manual jobs and gives the manual jobs priority over scheduled jobs.
The server returns a **DeduplicationJob** object for each job that you start with this cmdlet.

For multi-volume data deduplication jobs, you can use the **Preempt** parameter to move a job to the
top of the job queue and cancel the current job.

## EXAMPLES

### Example 1: Start an optimization job

```powershell
Start-DedupJob -Volume "D:" -Type Optimization -Memory 50
```

This command starts a deduplication optimization job on drive `D:` and consume up to a maximum of
`50` percent of RAM.

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

Specifies the maximum percentage of physical cores that a job uses.

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
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputOutputThrottle

Specifies the amount of input/output throttling applied to the deduplication job. Throttling ensures
that deduplication does not interfere with other I/O intensive processes. The acceptable values for
this parameter are: integers from `0` to `100`. If you specify this parameter and the
**InputOutputThrottleLevel** parameter, **InputOutputThrottle** takes precedence.

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

### -InputOutputThrottleLevel

Specifies the amount of I/O throttling that the job provides to ensure that the job does not
interfere with other I/O intensive processes. The acceptable values for this parameter are:

- `None`
- `Low`
- `Medium`
- `High`

If you specify this parameter and the **InputOutputThrottle** parameter, **InputOutputThrottle**
takes precedence.

```yaml
Type: InputOutputThrottleLevel
Parameter Sets: (All)
Aliases:
Accepted values: None, Low, Medium, High, Maximum

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### -Preempt

Indicates that the deduplication engine moves the job to the top of the job queue and cancels the
current job. After the server cancels the current job, the deduplication engine cannot run the
preempting job if the server does not have enough memory to run the job.

This parameter applies to manual data deduplication jobs only and is ignored for scheduled jobs. You
can preempt only deduplication jobs on multiple volumes.

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

### -Priority

Sets the CPU and I/O priority for the optimization job run that you run by using this cmdlet. For
jobs that you run when you specify the **StopWhenSystemBusy** parameter, we recommend that you set
this parameter to `Low`. For typical optimization jobs, we recommend that you set this parameter to
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

Indicates that the scrubbing job process and report on corruptions that it finds but does not run
any repair actions.

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
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Timestamp

Specifies a date and time. This parameter applies only to unoptimization jobs. The deduplication
engine unoptimizes only files that it optimized or reoptimized since the **System.DateTime** value
that you specify.

```yaml
Type: System.DateTime
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
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Volume

Specifies an array of system volumes for which you want to manually queue data deduplication jobs.
Enter one or more volume IDs, drive letters, or volume GUID paths. For drive letters, use the format
`D:`. For volume GUID paths, use the format `\\?\Volume{{GUID}}\`. Separate multiple volumes with a
comma.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: Path, Name, DeviceId

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Wait

Indicates that the cmdlet waits for the job to complete and provides progress information to the
client.

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

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.Management.Automation.SwitchParameter

### System.String[]

### System.UInt32

### Microsoft.PowerShell.Cmdletization.GeneratedTypes.DedupJob.Priority

### Microsoft.PowerShell.Cmdletization.GeneratedTypes.DedupJob.Type

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance

The **Microsoft.Management.Infrastructure.CimInstance** object is a wrapper class that displays
Windows Management Instrumentation (WMI) objects. The path after the pound sign (`#`) provides the
namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Get-DedupJob](./Get-DedupJob.md)

[Stop-DedupJob](./Stop-DedupJob.md)
