---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: DedupVolume.cdxml-help.xml
Module Name: Deduplication
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/deduplication/disable-dedupvolume?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-DedupVolume
---

# Disable-DedupVolume

## SYNOPSIS
Disables data deduplication activity on one or more volumes.

## SYNTAX

```
Disable-DedupVolume [-Volume] <String[]> [-DataAccess] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION

The `Disable-DedupVolume` cmdlet disables further data deduplication activity on one or more
volumes. After you disable data deduplication, the volume remains in a deduplicated state and the
existing deduplicated data is accessible. The server stops running data deduplication jobs for the
volume and new data is not deduplicated. To undo data deduplication on a volume, use the
`Start-DedupJob` cmdlet and specify `Unoptimization` for the **Type** parameter.

After you disable data deduplication on a volume, you can perform all read-only deduplication cmdlet
operations on the volume. For example, you can use the `Get-DedupStatus` cmdlet to get deduplication
status for a volume that has data deduplication metadata. After you disable data deduplication on a
volume, you cannot use the data deduplication job-related cmdlets and the `Update-DedupStatus`
cmdlet to perform operations on the volume. For example, you cannot use `Start-DedupJob` to start a
data deduplication job for a volume on which you have disabled data deduplication.

## EXAMPLES

### Example 1: Disable data deduplication on volumes

```powershell
Disable-DedupVolume -Volume "D:","E:","F:","G:"
```

This command disables data deduplication for volumes `D:`, `E:`, `F:`, and `G:`.

### Example 2: Disable data deduplication on a volume by using a GUID

```powershell
Disable-DedupVolume -Volume "\\?\Volume{26a21bda-a627-11d7-9931-806e6f6e6963}\"
```

This command disables data deduplication for the volume that has the GUID
`26a21bda-a627-11d7-9931-806e6f6e6963`.

### Example 3: Suspend I/O activity for a specified volume

```powershell
Disable-DedupVolume -Volume "X:" -DataAccess
```

This command suspends I/O activity for data deduplication on the specified volume. Effectively, this
command causes the data deduplication file system mini-filter to detach from the specified volume.
After this command completes, I/O to data deduplication files fails with an `ERROR_INVALID_FUNCTION`
error until either the `Enable-DedupVolume -DataAccess` command runs, or the server restarts.

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

### -DataAccess

Indicates that data access to deduplicated files on the volume is disabled.

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

Specifies an array of system volumes for which to disable data deduplication. Specify one or more
volume IDs, drive letters, or volume GUID paths. For drive letters, use the format `D:`. For volume
GUID paths, use the format `\\?\Volume{{GUID}}\`. Separate multiple volumes with a comma.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: DeviceId, Path, Name

Required: True
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

## NOTES

## RELATED LINKS

[Enable-DedupVolume](./Enable-DedupVolume.md)

[Get-DedupVolume](./Get-DedupVolume.md)

[Set-DedupVolume](./Set-DedupVolume.md)

[Update-DedupStatus](./Update-DedupStatus.md)
