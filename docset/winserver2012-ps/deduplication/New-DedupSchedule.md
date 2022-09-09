---
external help file: Dedup_Cmdlets.xml
Module Name: Deduplication
online version: https://docs.microsoft.com/powershell/module/deduplication/new-dedupschedule?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# New-DedupSchedule

## SYNOPSIS
Creates a data deduplication schedule.

## SYNTAX

```
New-DedupSchedule [-Name] <String> [-Type] <Type> [-AsJob] [-CimSession <CimSession[]>] [-Days] [-Disable]
 [-DurationHours <UInt32>] [-Full] [-Memory <UInt32>] [-Priority <Priority>] [-ReadOnly] [-Start <DateTime>]
 [-StopWhenSystemBusy] [-ThrottleLimit <Int32>]
```

## DESCRIPTION
The **New-DedupSchedule** cmdlet creates a data deduplication schedule.
This cmdlet returns a **DeduplicationSchedule** object that you can use to customize the data deduplication schedule.
This cmdlet uses default settings to create a data deduplication schedule for the parameters that you do not specify.

You can create a schedule to run the following types data deduplication jobs:

- Optimization: This type of job performs both deduplication and compression of files according data deduplication policy for the volume. After initial optimization of a file, if that file is then modified and again meets the data deduplication policy threshold for optimization, the file is optimized again. 
- GarbageCollection: This job processes deleted or modified data on the volume so that any data chunks that are no longer referenced are cleaned up. Garbage collection jobs process previously deleted or logically overwritten optimized content to create usable volume free space. When an optimized file is deleted or overwritten by new data, the old data in the chunk store is not immediately deleted. Garbage collection is scheduled to run weekly by default. Garbage collection is a processing-intensive operation, so you should allow the deletion load to reach a threshold and then manually run this job type, or schedule it for off hours.
- Scrubbing: This job processes data corruptions it finds during data integrity validation, performs possible corruption repair, and generates a scrubbing report. 
- Unoptimization: This job undoes data deduplication on all of the optimized files on the volume. At the end of a successful unoptimization job, the server deletes all of the data deduplication metadata from the volume.

For more information, see [Install and Configure Data Deduplication](https://technet.microsoft.com/library/hh831434.aspx) on TechNet.

## EXAMPLES

### Example 1: Create a data deduplication schedule for a garbage collection job
```
PS C:\>New-DedupSchedule -Name "OffHoursGC" -Type GarbageCollection -Start 08:00 -DurationHours 5 -Days Sun -Priority Normal
```

This command creates a data deduplication schedule for a garbage collection job named OffHoursGC.
The job is scheduled to run on Sundays at 8:00 at normal priority.
The command specifies that the server cancels the job after 5 hours if the process has not ended.

### Example 2: Create a data deduplication schedule for a scrubbing job
```
PS C:\>New-DedupSchedule -Name "OffHoursScrub" -Type Scrubbing -Start 23:00 -StopWhenSystemBusy -DurationHours 6 -Days Mon,Tues,Wed,Thurs,Fri -Priority Normal
```

This command creates a data deduplication schedule for a scrubbing job named OffHoursScrub.
The command starts the scrubbing job at 23:00 on Monday through Friday at normal priority.
The **StopWhenSystemBusy** parameter specifies that the server stops the job when the system is busy and retries later.
The **DurationHours** parameter specifies that the server cancels the job after 6 hours if the process has not ended.

### Example 3: Create a data deduplication schedule for an optimization job
```
PS C:\>New-DedupSchedule -Name "MyWeekendOptimization" -Type Optimization -Days Mon,Tues,Wed,Thurs,Fri -Start 08:00 -DurationHours 9
```

This command creates a data deduplication schedule for an optimization job named MyWeekdayOptimization.
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
Enter a computer name or a session object, such as the output of a [New-CimSession](/powershell/module/cimcmdlets/new-cimsession) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
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
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Disable
Indicates that the server disables the data deduplication schedule immediately after you create it.
The server does not run the data deduplication schedule at the time that you specify in the **Start** parameter.
After you disable a data deduplication schedule, you can use the Set-DedupSchedule cmdlet to enable the schedule.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Accept pipeline input: True (ByPropertyName)
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
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Memory
Specifies the maximum percentage of physical computer memory that the data deduplication job can use.

For optimization jobs, we recommend that you set a range from 15 to 50, and a higher memory consumption for jobs that you schedule to run when you specify the **StopWhenSystemBusy** parameter.
For garbage collection and scrubbing jobs, which you typically schedule to run in off hours, you can set a higher memory consumption, such as 50.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies a name for the data deduplication job schedule.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
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
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ReadOnly
Indicates that the scrubbing job processes and reports on corruptions that it finds but does not run any repair actions.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StopWhenSystemBusy
Indicates that the server stops the job when the system is busy and retries later.
We recommend that you specify this parameter when you set a low priority for the job.

```yaml
Type: SwitchParameter
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

### -Type
Specifies the type of data deduplication job.
The acceptable values for this parameter are:
- Optimization
- GarbageCollection
- Scrubbing
- Unoptimization

```yaml
Type: Type
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: Optimization
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

## INPUTS

### System.DateTime

### System.DayOfWeek[]

### System.Management.Automation.SwitchParameter

### System.UInt32

### Microsoft.PowerShell.Cmdletization.GeneratedTypes.DedupSchedule.Priority

### Microsoft.PowerShell.Cmdletization.GeneratedTypes.DedupSchedule.Type

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Get-DedupSchedule](./Get-DedupSchedule.md)

[Remove-DedupSchedule](./Remove-DedupSchedule.md)

[Set-DedupSchedule](./Set-DedupSchedule.md)
