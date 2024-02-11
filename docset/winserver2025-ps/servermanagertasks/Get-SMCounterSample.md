---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: ServerManagerTasks.cdxml-help.xml
Module Name: ServerManagerTasks
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/servermanagertasks/get-smcountersample?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-SMCounterSample
---

# Get-SMCounterSample

## SYNOPSIS
Gets performance counter samples for a particular time or period of time.

## SYNTAX

### InTimeRange (Default)
```
Get-SMCounterSample -CollectorName <String> -CounterPath <String[]> [-BatchSize <UInt32>]
 [-StartTime <DateTime>] [-EndTime <DateTime>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### AtTime
```
Get-SMCounterSample -CollectorName <String> -CounterPath <String[]> -Timestamp <DateTime[]>
 [-BatchSize <UInt32>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SMCounterSample** cmdlet gets performance counter samples for a specified time and performance counter.
Before you can run this cmdlet, performance data collection must be started on the target computer; after starting performance data collection, allow 30 minutes for collection.
You can start performance data collection by running the Start-SMPerformanceCollector cmdlet; you can also start performance data collection by right-clicking the row for a server that is displayed in the Performance tile of a Server Manager role or group page, and then clicking Start Performance Counters.

## EXAMPLES

### Example 1: Get counter samples from the preceding 24 hours
```
PS C:\>Get-SMCounterSample -BatchSize 100 -EndTime (Get-Date) -StartTime (Get-Date).AddDays(-1) -CollectorName 'Server Manager Performance Monitor' -CounterPath '\Process(System)\% Processor Time'
```

This command gets performance counter samples for the \Process(System)\% Processor Time counter path within the Server Manager Performance Monitor collector set, running on the local server.
The start time is set to 24 hours before the current time, and the end time is set to the current time.
The batch size is set to 100 records.

### Example 2: Get a counter sample at a specific time
```
PS C:\>Get-SMCounterSample -CollectorName 'Server Manager Performance Monitor' -CounterPath '\Process(PowerShell)\Thread Count' -TimeStamp '3/19/2014 3:27:24 PM'
```

This command gets performance counter samples collected at a specific time for the \Process(PowerShell)\Thread Count counter path within the Server Manager Performance Monitor collector set, running on the local server.
Because no batch size is specified, a message informs you that the default batch size of 256 records is used.
Note that this command returns results only if a performance counter sample was taken precisely at the specified time stamp.
If the specified time stamp does not correspond to a time at which counter samples were collected, the command returns no results.

### Example 3: Get counter samples for multiple paths, from a remote server
```
PS C:\>$RemoteSession = New-CimSession -ComputerName ServerManagerClient -Credential (Get-Credential)
PS C:\>Get-SMCounterSample -BatchSize 200 -CimSession $RemoteSession -CounterPath @('\Memory\Available Kbytes','\Process(iexplore)\% Processor Time','\Process(iexplore)\IO Data Bytes/sec') -CollectorName 'Server Manager Performance Monitor' -EndTime (Get-Date)-StartTime (Get-Date).AddDays(-1)
```

This command gets performance counter samples collected on a remote server for the \Memory\Available Kbytes, \Process(iexplore)\% Processor Time, and \Process(iexplore)\IO Data Bytes/sec counter paths, in the Server Manager Performance Monitor collector set.
You must be a member of the Administrators group on a remote server to run this command, and the remote server must be running Windows Server 2012 or a newer release of Windows Server.

The first line creates a new CIM session targeted at a remote server, ServerManagerClient, and prompts for credentials by running (Get-Credential) as the value of the Credential parameter.

The next line of the command gets performance counter samples for Internet Explorer and available memory for the preceding 24 hours.
The CIM session variable from the first line of the command is applied to get the samples from the remote server, ServerManagerClient.

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to complete.

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
Specifies the batch size of results; in this case, the number of performance counter samples returned.
If you do not specify a batch size, the default value is 256.

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

### -CollectorName
Specifies the name of the data collector set in Performance Log Analyzer (PLA) to query.
The collector name for Server Manager is 'Server Manager Performance Monitor'; because this name contains spaces, it must be specified in your command in quotations, as shown here.
If desired, you can create a custom data collector set in Performance Logs and Alerts (PLA).
For more information about how to create a custom data collector set, see [Creating a Collector Set](https://msdn.microsoft.com/library/windows/desktop/bb509347.aspx) and [Create a Data Collector Set Manually](https://technet.microsoft.com/library/cc766404.aspx).

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
The following are valid values for the counter path, within the Server Manager Performance Monitor.
To return performance counter samples for all processes, keep the asterisk (*) in the value; to return samples for a specific process, replace the asterisk with a process name, such as System.
To get performance counter samples for multiple paths, specify an array as a value for this parameter, placing quotations around paths, and separating paths with commas, as shown in the following example: @(' Process(*)\% Processor Time','\Memory\Available KBytes').
\Processor(_Total)\% Processor Time
\Memory\Available KBytes
\Process(*)\% Processor Time
\Process(*)\IO Data Bytes/sec
\Process(*)\Private Bytes
\Process(*)\Thread Count
\Process(*)\ID Process

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
The value of this parameter is in the format System.DateTime.
A simple way of providing an end time that is the same as the current time is to specify (Get-Date) as the value of the parameter.

```yaml
Type: DateTime
Parameter Sets: InTimeRange
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StartTime
Specifies a start time for the sample data collection.
The value of this parameter is in the format System.DateTime.

```yaml
Type: DateTime
Parameter Sets: InTimeRange
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


```yaml
Type: DateTime[]
Parameter Sets: AtTime
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#MSFT_ServerPerformanceCounterSamples[]

## NOTES

## RELATED LINKS

