---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: StorageScripts-help.xml
Module Name: Storage
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/storage/get-storagehealthreport?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-StorageHealthReport
---

# Get-StorageHealthReport

## SYNOPSIS
Gets a storage health report.

## SYNTAX

```
Get-StorageHealthReport -InputObject <CimInstance> [-Count <Int32>] [-CimSession <CimSession>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-StorageHealthReport** cmdlet gets a storage health report.

## EXAMPLES

### Example 1: Get a storage health report
```
PS C:\>Get-StorageSubSystem -Model "Clustered Windows Storage" | Get-StorageHealthReport
AverageCPUUsage           :  10.73 %
AverageLatency            :      0 ns
MemoryAvailable           :  82.84 GB
MemoryTotal               :     96 GB
PhysicalCapacityRemaining : 139.24 GB
PhysicalCapacityTotal     :  336.7 GB
PoolCapacityRemaining     : 161.25 GB
PoolCapacityTotal         :    185 GB
ReadIOPS                  :      0 /S
ReadLatency               :      0 ns
ReadThroughput            :      0 B/S
TotalIOPS                 :      0 /S
TotalThroughput           :      0 B/S
VolumeCapacityRemaining   :   4.92 GB
VolumeCapacityTotal       :   5.97 GB
WriteIOPS                 :      0 /S
WriteLatency              :      0 ns
WriteThroughput           :      0 B/S
ExtendedStatus :
ReturnValue    : 0
PSComputerName :
```

This command uses the Get-StorageSubSystem cmdlet to get the specified **StorageSubsystem** object, and uses the pipeline operator to pass it to **Get-StorageHealthReport** to display its health report.

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

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Count
Specifies the number of report objects to be collected when the report runs.
The default value is one (1).
The maximum value is 300.

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

### -InputObject
Specifies the input object that is used in a pipeline command.

```yaml
Type: CimInstance
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#MSFT_StorageHealthReport

## NOTES

* When used in Failover Cluster, cmdlets from the Storage module operate on cluster level (all servers in the cluster).

## RELATED LINKS

[Get-StorageSubSystem](./Get-StorageSubsystem.md)

