---
external help file: Dedup_Cmdlets.xml
online version: 
schema: 2.0.0
ms.assetid: ED2C90F6-5605-4041-93CD-CF179D010631
manager: dansimp
ms.reviewer:
ms.author: kenwith
author: kenwith
---

# Remove-DedupSchedule

## SYNOPSIS
Deletes the specified DeduplicationSchedule object.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Remove-DedupSchedule [-Name] <String[]> [-AsJob] [-CimSession <CimSession[]>] [-PassThru]
 [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_2
```
Remove-DedupSchedule [-AsJob] [-CimSession <CimSession[]>] [-PassThru] [-ThrottleLimit <Int32>]
 -InputObject <CimInstance[]>
```

## DESCRIPTION
The **Remove-DedupSchedule** cmdlet deletes the specified DeduplicationSchedule object.

To run this cmdlet, you must start Windows PowerShell® with the **Run as administrator** option.

## EXAMPLES

### Example 1
```
PS C:\>Remove-DedupSchedule -Name MyDailyOptimization
```

This example deletes the DeduplicationJobSchedule object named MyDailyOptimization.

### Example 2
```
PS C:\>Remove-DedupSchedule -Type Unoptimization
```

This example deletes all unoptimized DeduplicationJobSchedule objects.

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

### -InputObject
Specifies the CIM instance object that represents the instance to be changed.
Enter a variable that contains the object, or type a cmdlet or expression that gets the object, such as the Get-DedupVolume cmdlet.
A service object can be piped to the Set-DedupVolume cmdlet.

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

### -Name
Specifies the friendly name of one or more data deduplication job schedules that will be removed.

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
Returns an object representing data deduplication settings to be removed and pushes it through to the pipeline.

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

### System.String[]

### Microsoft.Management.Infrastructure.CimInstance#
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

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

[Set-DedupSchedule](./Set-DedupSchedule.md)

