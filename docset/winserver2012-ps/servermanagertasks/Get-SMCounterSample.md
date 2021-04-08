---
author: Kateyanne
external help file: SMTasks_Cmdlets.xml
manager: dansimp
Module Name: ServerManagerTasks
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/servermanagertasks/get-smcountersample?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-SMCounterSample

## SYNOPSIS
Gets performance counter samples for a particular time stamp.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-SMCounterSample [-AsJob] [-BatchSize <UInt32>] [-CimSession <CimSession[]>] [-EndTime <DateTime>]
 [-StartTime <DateTime>] [-ThrottleLimit <Int32>] -CollectorName <String> -CounterPath <String[]>
```

### UNNAMED_PARAMETER_SET_2
```
Get-SMCounterSample [-AsJob] [-BatchSize <UInt32>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 -CollectorName <String> -CounterPath <String[]> -Timestamp <DateTime[]>
```

## DESCRIPTION
The **Get-SMCounterSample** cmdlet gets performance counter samples for a particular time.

## EXAMPLES

### Example 1: Get a counter sample from a data collector set
```
PS C:\>Get-SMCounterSample -CollectorName "ContosoPerf" -CounterPath "C:\PerfLogs\Admin\"-EndTime 12:00 -StartTime 11:00
```

This command gets the performance sample for the collector named ContosoPerf and the counter path specified as C:\PerfLogs\Admin\ within a specified timeframe.

### Example 2: Get a counter sample at a specified time
```
PS C:\>Get-SMCounterSample -CollectorName "ContosoPerf" -CounterPath "C:\PerfLogs\Admin\" -TimeStamp @(1,3,5,7)
```

This command gets the performance sample for the collector named ContosoPerf and the counter path named C:\PerfLogs\Admin\ at a specified time.
The timestamp is an array of **DateTime** objects.

## PARAMETERS

### -AsJob
ps_cimcommon_asjob

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

### -BatchSize
Specifies the batch size that the command uses to stream results.

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

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a New-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227967 or Get-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227966 cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CollectorName
Specifies the name of the data collector set in Performance Log Analyzer (PLA) to query.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CounterPath
Specifies an array of paths to the counter data.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EndTime
Specifies the end time for the sample data collection.

```yaml
Type: DateTime
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StartTime
Specifies a start time for the sample data collection.

```yaml
Type: DateTime
Parameter Sets: UNNAMED_PARAMETER_SET_1
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

### -Timestamp
Specifies an array of **DateTime** objects.
The objects specify when the sampling occurs.

```yaml
Type: DateTime[]
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#MSFT_ServerPerformanceCounterSamples[]

## NOTES

## RELATED LINKS



