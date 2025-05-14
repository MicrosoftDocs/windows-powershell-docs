---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: DedupVolume.cdxml-help.xml
Module Name: Deduplication
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/deduplication/set-dedupvolume?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-DedupVolume
---

# Set-DedupVolume

## SYNOPSIS
Changes data deduplication settings on one or more volumes.

## SYNTAX

### ByVolumeId (Default)

```
Set-DedupVolume [-VolumeId <String[]>] [-OptimizeInUseFiles] [-OptimizePartialFiles]
 [-NoCompress <Boolean>] [-Verify <Boolean>] [-MinimumFileAgeDays <UInt32>]
 [-MinimumFileSize <UInt32>] [-ChunkRedundancyThreshold <UInt32>]
 [-ExcludeFolder <String[]>] [-ExcludeFileType <String[]>]
 [-ExcludeFileTypeDefault <String[]>] [-NoCompressionFileType <String[]>]
 [-InputOutputScale <UInt32>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [-PassThru] [<CommonParameters>]
```

### ByVolume

```
Set-DedupVolume [-Volume] <String[]> [-OptimizeInUseFiles] [-OptimizePartialFiles]
 [-NoCompress <Boolean>] [-Verify <Boolean>] [-MinimumFileAgeDays <UInt32>]
 [-MinimumFileSize <UInt32>] [-ChunkRedundancyThreshold <UInt32>]
 [-ExcludeFolder <String[]>] [-ExcludeFileType <String[]>]
 [-ExcludeFileTypeDefault <String[]>] [-NoCompressionFileType <String[]>]
 [-InputOutputScale <UInt32>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [-PassThru] [<CommonParameters>]
```

### InputObject (cdxml)

```
Set-DedupVolume -InputObject <CimInstance[]> [-OptimizeInUseFiles] [-OptimizePartialFiles]
 [-NoCompress <Boolean>] [-Verify <Boolean>] [-MinimumFileAgeDays <UInt32>]
 [-MinimumFileSize <UInt32>] [-ChunkRedundancyThreshold <UInt32>]
 [-ExcludeFolder <String[]>] [-ExcludeFileType <String[]>]
 [-ExcludeFileTypeDefault <String[]>] [-NoCompressionFileType <String[]>]
 [-InputOutputScale <UInt32>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [-PassThru] [<CommonParameters>]
```

## DESCRIPTION

The `Set-DedupVolume` cmdlet changes data deduplication settings on one or more volumes.

## EXAMPLES

### Example 1: Set the exclude folders on a volume

```powershell
Set-DedupVolume -Volume "F:" -ExcludeFolder "F:\temp","F:\SQL"
```

This command sets the root folders under which all files are skipped during data deduplication. The
**ExcludeFolder** parameter specifies that the data deduplication engine processes the files in all
of the folders on volume `F:` except for files in the Temp folder and the SQL folder. If you exclude
folders that contain previously optimized files, this command does not unoptimize those files. You
have to manually unoptimize any previously optimized files specified by **ExcludeFolder**.

Note if the ExcludeFolder already contains optimized files, those optimized files are not
automatically unoptimized by this command. Any previously optimized files under the ExcludeFolder
will need to be manually unoptimized.

### Example 2: Set the minimum file age on a volume

```powershell
Set-DedupVolume -Volume "E:" -MinimumFileAgeDays 10
```

This command sets the number of days since the file was created before the deduplication engine
optimizes the file. The **MinimumFileAgeDays** parameter specifies that the data deduplication
engine processes the files in all of the folders on volume `E:` that were created at least `10` days
ago.

### Example 3: Set the chunk redundancy threshold on a volume

```powershell
Set-DedupVolume -Volume "D:" -MinimumFileAgeDays 15 -ChunkRedundancyThreshold 50
```

This command sets the number of identical chunks of data that the deduplication engine encounters
during deduplication before the server creates a redundant copy of the data chunk. The
**MinimumFileAgeDays** parameter specifies that the data deduplication engine processes the files in
all of the folders on volume `D:` that were created at least `15` days ago. The
**ChunkRedundancyThreshold** parameter specifies that if the data deduplication engine discovers
`50` chunks of identical data, it makes one redundant copy as a safeguard.

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

### -ChunkRedundancyThreshold

Specifies the number of identical chunks of data that the deduplication engine encounters before the
server creates a redundant copy of the data chunk. This increases the reliability of the server by
adding redundancy to the most referenced chunks of data.

Deduplication detects corruptions and the deduplication scrubbing job restores the corrupted chunks
from a redundant copy, if it is available. The default value is `100`. The minimum value that you
can set is `20`. A low value for the **ChunkRedundancyThreshold** parameter reduces the
effectiveness of data deduplication by creating more redundant copies of a chunk, and consumes more
memory and disk space.

```yaml
Type: System.UInt32
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

### -ExcludeFileType

Specifies an array of extension types that the deduplication engine excludes from data deduplication
and optimization. Specify comma-separated values that are not preceded with a period (`.`). When you
change this setting, you override the existing values.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExcludeFileTypeDefault

Specifies an array of extension types, as strings, that the server does not optimize.

The `Enable-DedupVolume` cmdlet modifies this behavior, depending on the value of the **UsageType**
parameter. If you use the current parameter to modify this behavior, and then run
`Enable-DedupVolume` again, that cmdlet overrides your changes.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExcludeFolder

Specifies an array of names of root folders under which all files are skipped during data
deduplication. Full paths are accepted, however mount points are ignored since the mount point can
change after configuration. When you change this setting, you override the existing values.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

Specifies the input to this cmdlet. You can use this parameter, or you can pipe the input to this
cmdlet.

```yaml
Type: Microsoft.Management.Infrastructure.CimInstance[]
Parameter Sets: InputObject (cdxml)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -InputOutputScale

Specifies the level of input/output parallelization during optimization for this volume. The
acceptable values for this parameter are: integers from `0` to `36`. The default value of `0` sets
the system to automatically select an **InputOutputScale** value based on the size of the volume to
deduplicate.

```yaml
Type: System.UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MinimumFileAgeDays

Number of days after the file is created before the file is considered to be in-policy for
optimization.

The `Default` and `HyperV` **UsageType** set this value to `3` to maximize performance on hot or
recently created files. You may want to modify this if you want Data Deduplication to be more
aggressive or if you do not care about the extra latency associated with deduplication.

```yaml
Type: System.UInt32
Parameter Sets: (All)
Aliases: MinimumFileAge

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MinimumFileSize

Specifies the minimum size threshold, in bytes, for files that are optimized. The deduplication
engine does not optimize files that do not meet the minimum threshold.

```yaml
Type: System.UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoCompress

Indicates whether or not the server compresses data after deduplication. Compression uses more
processor cycles but provides additional space savings.

```yaml
Type: System.Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoCompressionFileType

Specifies an array of file types that the deduplication engine excludes from compression. These file
types are deduplicated but not compressed, typically because the file format is already compressed.
Specify comma-separated values that are not preceded with a period (`.`). When you change this
setting, you override the existing values.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OptimizeInUseFiles

Indicates that the server attempts to optimize currently open files. After specifying this
parameter, the server may wait up to 15 minutes before it attempts to optimize open files.

`Enable-DedupVolume` modifies this behavior, depending on the value of the **UsageType** parameter.
If you use the current parameter to modify this behavior, and then run `Enable-DedupVolume` again,
that cmdlet overrides your changes.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -OptimizePartialFiles

Indicates that the server optimizes all files, including portions of files that are old enough,
according to the value of the **MinimumFileAgeDays** parameter.

`Enable-DedupVolume` modifies this behavior, depending on the value of the **UsageType** parameter.
If you use the current parameter to modify this behavior, and then run `Enable-DedupVolume` again,
that cmdlet overrides your changes.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru

Returns an object representing the item with which you are working. By default, this cmdlet does not
generate any output.

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

### -Verify

Indicates whether the deduplication engine performs a byte-for-byte verification for each duplicate
chunk that optimization creates, rather than relying on a cryptographically strong hash. We do not
recommend that you use this parameter. Setting this parameter to $True can degrade optimization
performance.

```yaml
Type: System.Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Volume

Specifies an array of system volumes. Specify one or more volume IDs, drive letters, or volume GUID
paths. For drive letters, use the format `D:`. For volume GUID paths, use the format
`\\?\Volume{{GUID}}\`. Separate multiple volumes with a comma.

```yaml
Type: System.String[]
Parameter Sets: ByVolume
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VolumeId

Specifies an array of volume IDs.

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

### Microsoft.Management.Infrastructure.CimInstance

The **Microsoft.Management.Infrastructure.CimInstance** object is a wrapper class that displays
Windows Management Instrumentation (WMI) objects. The path after the pound sign (`#`) provides the
namespace and class name for the underlying WMI object.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance

The **Microsoft.Management.Infrastructure.CimInstance** object is a wrapper class that displays
Windows Management Instrumentation (WMI) objects. The path after the pound sign (`#`) provides the
namespace and class name for the underlying WMI object.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Deduplication/MSFT_DedupVolume

## NOTES

## RELATED LINKS

[Disable-DedupVolume](./Disable-DedupVolume.md)

[Enable-DedupVolume](./Enable-DedupVolume.md)

[Get-DedupVolume](./Get-DedupVolume.md)
