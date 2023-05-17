---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: DedupStatus.cdxml-help.xml
Module Name: Deduplication
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/deduplication/update-dedupstatus?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Update-DedupStatus
---

# Update-DedupStatus

## SYNOPSIS
Scans volumes for fresh data deduplication savings.

## SYNTAX

```
Update-DedupStatus [[-Volume] <String[]>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION

The `Update-DedupStatus` cmdlet scans one or more specified volumes to compute fresh data
deduplication savings information. This cmdlet returns a **DeduplicationStatus** object. For quick
access to cached metadata use `Get-DedupStatus`. When this cmdlet is run on multiple volumes with
one cmdlet call, the analysis for each volume is done serially.

> [!NOTE]
> On large volumes this cmdlet can run for several minutes and will always perform a rescan after
> the initial scan. The default behavior is to wait for completion, regardless of the length of
> time required to run the scan and rescan.

To run this cmdlet, you must start Windows PowerShell® with the **Run as administrator** option.

This cmdlet returns the following metadata:

- `DedupSavedSpace`
  - Saved space is the difference between the logical size of the optimized files
  and the logical size of the store. This is the deduplicated user data plus data deduplication
  metadata. This number changes continually.
- `DedupRate`
  - Data deduplication rate is the ratio of data deduplication saved space to the logical
  size of all of the files on the volume and is expressed in percentage. This number will change
  continually.
- `OptimizedFilesCount`
  - Optimized files count is the number of optimized files on the specified volume. This number
    remains steady, instead of decreasing, as users delete files from, or add files to, the volume,
    until a garbage collection job is run. This count is most accurate after a garbage collection
    job runs.
- `OptimizedFilesSize`
  - Optimized files size is the aggregate size of all optimized files on the specified volume. This
    number remains steady, instead of decreasing, as users delete files from, or add new files to,
    the volume, until a garbage collection job is run. This number is most accurate after a garbage
    collection job runs.
- `InPolicyFilesCount`
  - In policy files count is the number of files that currently qualify for optimization. This
    number stays relatively constant between optimization jobs.
- `InPolicyFilesSize`
  - In policy files size is the aggregate size of all files that currently qualify for optimization.
    This number stays relatively constant between optimization jobs.
- `LastOptimizationTime`
  - Last optimization time specifies the data and time when an optimization job was run last on the
    specified volume. This date and time stays constant between optimization jobs.
- `LastGarbageCollectionTime`
  - Last garbage collection time specifies the data and time when a garbage collection job was run
    last on the specified volume. This date and time stays constant between optimization jobs.
- `LastScrubbingTime`
  - Last scrubbing time specifies the data and time when a scrubbing job was run last on the
    specified volume. This date and time stays constant between optimization jobs.

## EXAMPLES

### Example 1: Scan a volume for savings information

```powershell
Update-DedupStatus -Volume "D:"
```

This command scans the `D:` volume to compute data deduplication savings.

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

Specifies one or more file system volumes for which to scan and compute fresh data deduplication
savings information. Enter one or more volume IDs, drive letters, or volume GUID paths. For drive
letters, use the format `D:`. For volume GUID paths, use the format `\\?\Volume{{GUID}}\`.
Separate multiple volumes with a comma.

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

## NOTES

## RELATED LINKS

[Get-DedupStatus](./Get-DedupStatus.md)
