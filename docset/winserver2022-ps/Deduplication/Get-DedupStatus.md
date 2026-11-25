---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: DedupStatus.cdxml-help.xml
Module Name: Deduplication
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/deduplication/get-dedupstatus?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-DedupStatus
---

# Get-DedupStatus

## SYNOPSIS
Returns deduplication status for volumes that have data deduplication metadata.

## SYNTAX

```
Get-DedupStatus [[-Volume] <String[]>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION

The `Get-DedupStatus` cmdlet returns a deduplication status object for every volume that has data
deduplication metadata. A **DeduplicationStatus** object includes read-only properties that describe
capacity, free or used space and optimization savings and status on the volume, times, and
completion status for the last jobs on the volume.

To run this cmdlet, you must start Windows PowerShell® with the **Run as administrator** option.

## EXAMPLES

### Example 1: Get status for specified volumes

```powershell
Get-DedupStatus -Volume "D:","F:"
```

This command gets deduplication status for the `D:` and `F:` volumes.

## PARAMETERS

### -AsJob\

Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to
complete.

The cmdlet immediately returns an object that represents the job and then displays the command
prompt. You can continue to work in the session while the job completes. To manage the job, use the
`*-Job` cmdlets. To get the job results, use the
[Receive-Job](https://go.microsoft.com/fwlink/?LinkID=113372) cmdlet.

For more information about Windows PowerShell background jobs, see
[about_Jobs](https://go.microsoft.com/fwlink/?LinkID=113251).

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CimSession

Runs the cmdlet in a remote session or on a remote computer. Enter a computer name or a session
object, such as the output of a [New-CimSession](/powershell/module/cimcmdlets/new-cimsession) or
[Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet. The default is the
current session on the local computer.

```yaml
Type: Microsoft.Management.Infrastructure.CimSession[]
Parameter Sets: (All)
Aliases: Session

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit

Specifies the maximum number of concurrent operations that can be established to run the cmdlet. If
this parameter is omitted or a value of `0` is entered, then Windows PowerShell® calculates an
optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the
computer. The throttle limit applies only to the current cmdlet, not to the session or to the
computer.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Volume

Specifies one or more file system volumes for which to return a DeduplicationStatus object. Enter
one or more volume IDs, drive letters, or volume GUID paths. For drive letters, use the format `D:`.
For volume GUID paths, use the format `\\?\Volume{{GUID}}\`. Separate multiple volumes with a
comma.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Path, Name, DeviceId

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String[]

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance

The **Microsoft.Management.Infrastructure.CimInstance** object is a wrapper class that displays
Windows Management Instrumentation (WMI) objects. The path after the pound sign (`#`) provides the
namespace and class name for the underlying WMI object.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Deduplication/MSFT_DedupVolumeStatus

The **Microsoft.Management.Infrastructure.CimInstance** object is a wrapper class that displays
Windows Management Instrumentation (WMI) objects. The path after the pound sign (`#`) provides the
namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Update-DedupStatus](./Update-DedupStatus.md)
