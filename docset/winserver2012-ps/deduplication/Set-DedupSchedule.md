---
external help file: Dedup_Cmdlets.xml
online version: 
schema: 2.0.0
ms.assetid: B5B6E091-C062-4A50-9E61-05F2AD282221
manager: dansimp
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Set-DedupSchedule

## SYNOPSIS
Changes configuration settings for data deduplication schedules.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Set-DedupSchedule [-Name] <String[]> [-AsJob] [-CimSession <CimSession[]>] [-Days] [-DurationHours <UInt32>]
 [-Enabled <Boolean>] [-Full <Boolean>] [-Memory <UInt32>] [-PassThru] [-Priority <Priority>]
 [-ReadOnly <Boolean>] [-Start <DateTime>] [-StopWhenSystemBusy <Boolean>] [-ThrottleLimit <Int32>]
 [-Type <Type[]>]
```

### UNNAMED_PARAMETER_SET_2
```
Set-DedupSchedule [-AsJob] [-CimSession <CimSession[]>] [-Days] [-DurationHours <UInt32>] [-Enabled <Boolean>]
 [-Full <Boolean>] [-Memory <UInt32>] [-PassThru] [-Priority <Priority>] [-ReadOnly <Boolean>]
 [-Start <DateTime>] [-StopWhenSystemBusy <Boolean>] [-ThrottleLimit <Int32>] -InputObject <CimInstance[]>
```

## DESCRIPTION
The **Set-DedupSchedule** cmdlet changes configuration settings for one or more data deduplication schedules.

## EXAMPLES

### Example 1: Change settings of a data deduplication schedule for a garbage collection job
```
PS C:\>Set-DedupSchedule -Name "OffHoursGC" -Type GarbageCollection -Start 08:00 -DurationHours 5 -Days Sun -Priority Normal
```

This command changes the settings of a data deduplication schedule for a garbage collection job named OffHoursGC.
The job is scheduled to run on Sundays at 8:00 at normal priority.
The command specifies that the server cancels the job after 5 hours if the process has not ended.

### Example 2: Change settings of a data deduplication schedule for a scrubbing job
```
PS C:\>Set-DedupSchedule -Name "OffHoursScrub" -Type Scrubbing -Start 23:00 -StopWhenSystemBusy $True -DurationHours 6 -Days Mon,Tues,Wed,Thurs,Fri -Priority Normal
```

This command changes the settings of a data deduplication schedule for a scrubbing job named OffHoursScrub.
The command starts the scrubbing job at 23:00 on Monday through Friday at normal priority.
The **StopWhenSystemBusy** parameter specifies that the server stops the job when the system is busy and retries later.
The **DurationHours** parameter specifies that the server cancels the job after 6 hours if the process has not ended.

### Example 3: Change settings of a data deduplication schedule for an optimization job
```
PS C:\>Set-DedupSchedule -Name "MyWeekendOptimization" -Type Optimization -Days Mon,Tues,Wed,Thurs,Fri -Start 08:00 -DurationHours 9
```

This command changes the settings of a data deduplication schedule for an optimization job named MyWeekdayOptimization.
The optimization job runs at a normal priority every weekday evening at 8:00.
**DurationHours** specifies that the server cancels the job after 9 hours if the process has not ended.

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
Enter a computer name or a session object, such as the output of a [New-CimSession](https://docs.microsoft.com/powershell/module/cimcmdlets/new-cimsession) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
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

### -Days
Specifies an array of days of the week on which the server runs the data deduplication job.
The acceptable values for this parameter are:
- Monday
- Tuesday
- Wednesday
- Thursday
- Friday
- Saturday
- Sunday

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 
Accepted values: Sunday, Monday, Tuesday, Wednesday, Thursday, Friday, Saturday

Required: False
Position: Named
Default value: Monday,Tuesday,Wednesday,Thursday,Friday,Saturday,Sunday
Accept pipeline input: False
Accept wildcard characters: False
```

### -DurationHours
Specifies the number of hours that the server runs the task before canceling it.
The value 0 indicates that the server runs the job to completion.
This cmdlet safely stops a data deduplication job and does not affect the files that the server is processing when it cancels the job.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: 2
Accept pipeline input: False
Accept wildcard characters: False
```

### -Enabled
Indicates whether or not a data deduplication schedule is enabled.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Full
If you specify GarbageCollection for the **Type** parameter: 
Indicates that garbage collection jobs free up all deleted or unreferenced data on the volume.
If you do not specify this parameter, garbage collection jobs free up space after a system threshold of delete data is exceeded.
We recommend that you run garbage collection regularly without specifying this parameter, and then once a month specify this parameter and run garbage collection again.

If you specify Scrubbing for the **Type** parameter: 
Indicates that scrubbing jobs validate the integrity of all data on the volume.
If you do not specify this parameter, the scrubbing job validates only critical metadata and data integrity issues that data deduplication previously encountered.
We recommend that you run scrubbing regularly without specifying this parameter, and then once a month specify this parameter and run scrubbing again.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Specifies the input to this cmdlet.
You can use this parameter, or you can pipe the input to this cmdlet.

```yaml
Type: CimInstance[]
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Memory
Specifies the maximum percentage of physical computer memory that the data deduplication job can use.

For optimization jobs, we recommend that you set a range from 15 to 50, and a higher memory consumption for jobs that you schedule to run when you specify the **StopWhenSystemBusy** parameter.
For garbage collection and scrubbing jobs, which you typically schedule to run in off hours, you can set higher memory consumption, such as 50.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of a data deduplication job schedule.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru
Returns an object representing the item with which you are working.
By default, this cmdlet does not generate any output.

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

### -Priority
Sets the CPU and I/O priority for the optimization job that you run by using this cmdlet.
For jobs that you run when you specify the **StopWhenSystemBusy** parameter, we recommend that you set this parameter to High.
For typical optimization jobs, we recommend that you set this parameter to Normal.

```yaml
Type: Priority
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ReadOnly
Indicates whether or not the scrubbing job processes and reports on corruptions that it finds but does not run any repair actions.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Start
Specifies a time to start this job.
The default value is 1:45am.

Type the date in a format that is standard for the system locale, such as dd-MM-yyyy (German \[Germany\]) or MM/dd/yyyy (English \[United States\]).

```yaml
Type: DateTime
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StopWhenSystemBusy
Indicates whether or not the server stops the job when the system is busy and retries later.
We recommend that you specify this parameter when you set a low priority for the job.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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

### -Type
Specifies an array of types of data deduplication jobs.
The acceptable values for this parameter are:
- Optimization
- GarbageCollection
- Scrubbing
- Unoptimization

```yaml
Type: Type[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

## INPUTS

### System.String[]

### Microsoft.Management.Infrastructure.CimInstance#

### Microsoft.PowerShell.Cmdletization.GeneratedTypes.DedupSchedule.Type[]

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Deduplication/MSFT_DedupJobSchedule
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Get-DedupSchedule](./Get-DedupSchedule.md)

[New-DedupSchedule](./New-DedupSchedule.md)

[Remove-DedupSchedule](./Remove-DedupSchedule.md)

