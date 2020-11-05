---
external help file: SMTasks_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: CB5682DE-A40F-4987-BC5B-C4B57F15D352
manager: dansimp
---

# Get-SMPerformanceCollector

## SYNOPSIS
Gets the state of the performance data collector set.

## SYNTAX

```
Get-SMPerformanceCollector [-AsJob] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 -CollectorName <String>
```

## DESCRIPTION
The **Get-SMPerformanceCollector** cmdlet gets the state of the data collector set in the Performance Log Analyzer (PLA).
A data collector set groups multiple data collection points, such as performance counters or events, into a single component.

## EXAMPLES

### Example 1:Get the performance data collector set state
```
PS C:\>Get-SMPerformanceCollector -CollectorName "ContosoPerf"
```

This command gets the state of the performance data collector set named ContosoPerf.

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
Specifies a data collector set in PLA.

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

## INPUTS

## OUTPUTS

### System.Byte
The output values and names are: 

- Value=0 Name="Stopped"
- Value=1 Name="Running"

## NOTES

## RELATED LINKS

[Start-SMPerformanceCollector](./Start-SMPerformanceCollector.md)

[Stop-SMPerformanceCollector](./Stop-SMPerformanceCollector.md)



