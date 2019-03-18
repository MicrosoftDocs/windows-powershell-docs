---
external help file: Dedup_Cmdlets.xml
online version: 
schema: 2.0.0
ms.assetid: AF82B937-D34A-4F57-B281-3C3E570FCCCF
ms.reviewer:
ms.author: kenwith
author: kenwith
---

# Get-DedupSchedule

## SYNOPSIS
Returns the DeduplicationJobSchedule objects defined on the system.

## SYNTAX

```
Get-DedupSchedule [[-Name] <String[]>] [-AsJob] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-Type <Type[]>]
```

## DESCRIPTION
The **Get-DedupSchedule** cmdlet returns the DeduplicationJobSchedule objects defined on the system.

To run this cmdlet, you must start Windows PowerShell® with the **Run as administrator** option.

## EXAMPLES

### Example 1
```
PS C:\>Get-DedupSchedule
```

This example returns the currently active DataDeduplicationSchedule objects created using the New-DedupSchedule cmdlet.

### Example 2
```
PS C:\>Get-DedupSchedule -Type Optimization
```

This example returns all data deduplication schedules for optimization jobs

### EXAMPLE 3
```
PS C:\>Get-DedupSchedule -Name MySchedule
```

This example returns the data deduplication schedule named MySchedule.

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
Aliases: Session

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the friendly name of one or more data deduplication job schedules for which to return DeduplicationJobSchedule objects.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
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
Specifies the names of one or more types of data deduplication job schedules for which to return DeduplicationJobSchedule objects.
The acceptable values for this parameter are: Optimization, GarbageCollection, Scrubbing, and Unoptimization.

```yaml
Type: Type[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

## INPUTS

### System.String[]

### Microsoft.PowerShell.Cmdletization.GeneratedTypes.DedupSchedule.Type[]

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Deduplication/MSFT_DedupJobSchedule
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[New-DedupSchedule](./New-DedupSchedule.md)

[Remove-DedupSchedule](./Remove-DedupSchedule.md)

[Set-DedupSchedule](./Set-DedupSchedule.md)

