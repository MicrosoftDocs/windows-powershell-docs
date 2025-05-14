---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: DedupVolume.cdxml-help.xml
Module Name: Deduplication
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/deduplication/get-dedupvolume?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-DedupVolume
---

# Get-DedupVolume

## SYNOPSIS
Returns deduplication volumes that have data deduplication metadata.

## SYNTAX

### ByVolumeId (Default)

```
Get-DedupVolume [-VolumeId <String[]>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByVolume

```
Get-DedupVolume [[-Volume] <String[]>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION

The `Get-DedupVolume` cmdlet returns a **DeduplicationVolume** object for each volume that has data
deduplication metadata, in either the enabled or disabled state. In a cluster, this cmdlet returns a
**DeduplicationVolume** object only for volumes currently mounted by the managed node, whether the
volumes are local or clustered volumes.

To run this cmdlet, you must start Windows PowerShell® with the **Run as administrator** option.

## EXAMPLES

### Example 1: Get settings for a volume identified by letter

```powershell
Get-DedupVolume -Volume "E:"
```

This command returns the data deduplication settings for volume `E:`.

### Example 2: Get settings for a volume specified by ID

```powershell
Get-DedupVolume -Volume "\\?\Volume{26a21bda-a627-11d7-9931-806e6f6e6963}\"
```

This command returns the data deduplication settings for the volume that has the specified GUID.

## PARAMETERS

### -AsJob

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
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Volume

Specifies one or more file system volumes for which to return data deduplication metadata, or in the
case of a cluster, volumes with data deduplication metadata currently mounted by the managed node.
Enter one or more volume IDs, drive letters, or volume GUID paths. For drive letters, use the format
`D:`. For volume GUID paths, use the format `\\?\Volume{{GUID}}\`. Separate multiple volumes with
a comma.

```yaml
Type: System.String[]
Parameter Sets: ByVolume
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VolumeId

Specifies a string that uniquely identifies the volume on which to return data deduplication
metadata.

```yaml
Type: System.String[]
Parameter Sets: ByVolumeId
Aliases: DeviceId, Path, Id

Required: False
Position: Named
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

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Deduplication/MSFT_DedupVolume

The **Microsoft.Management.Infrastructure.CimInstance** object is a wrapper class that displays
Windows Management Instrumentation (WMI) objects. The path after the pound sign (`#`) provides the
namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Disable-DedupVolume](./Disable-DedupVolume.md)

[Enable-DedupVolume](./Enable-DedupVolume.md)

[Set-DedupVolume](./Set-DedupVolume.md)
