---
external help file: SMTasks_Cmdlets.xml
Module Name: ServerManagerTasks
online version: https://learn.microsoft.com/powershell/module/servermanagertasks/stop-smperformancecollector?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Stop-SMPerformanceCollector

## SYNOPSIS
Stops a data collector set.

## SYNTAX

```
Stop-SMPerformanceCollector [-AsJob] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 -CollectorName <String> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Stop-SMPerformanceCollector** cmdlet stops a data collector set.
A data collector set groups multiple data collection points, such as performance counters or events, into a single component.

## EXAMPLES

### Example 1:
```
PS C:\>Stop-SMPerformanceCollector -CollectorName "ContosoPerf"
```

This command stops the performance data collector specified in the data collector set named ContosoPerf.

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

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-SMPerformanceCollector](./Get-SMPerformanceCollector.md)

[Start-SMPerformanceCollector](./Start-SMPerformanceCollector.md)



