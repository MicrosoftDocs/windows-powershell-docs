---
external help file: SMTasks_Cmdlets.xml
Module Name: ServerManagerTasks
online version: https://docs.microsoft.com/powershell/module/servermanagertasks/remove-smserverperformancelog?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Remove-SMServerPerformanceLog

## SYNOPSIS
Removes Server Manager performance log files.

## SYNTAX

```
Remove-SMServerPerformanceLog [-AsJob] [-CimSession <CimSession[]>] [-ThresholdMSec <UInt64>]
 [-ThrottleLimit <Int32>] -CollectorName <String> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Remove-SMServerPerformanceLog** cmdlet removes the performance log files that Server Manager performance counters generate.

## EXAMPLES

### Example 1:
```
PS C:\>Remove-SMServerPerformanceLog -CollectorName "ContosoPerf"
```

This command removes the performance logs for the data collector set named ContosoPerf.

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
Specifies the name of the data collector set in Performance Log Analyzer (PLA).

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

### -ThresholdMSec
Specifies the number of milliseconds that the command waits.

```yaml
Type: UInt64
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

### Microsoft.Management.Infrastructure.CimInstance#MSFT_ServerPerformanceAlerts[], System.DateTime

## NOTES

## RELATED LINKS



