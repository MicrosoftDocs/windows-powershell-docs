---
external help file: Dedup_Cmdlets.xml
online version: 
schema: 2.0.0
ms.assetid: D56A51BB-0B15-4BF9-AF3D-1EB96C1BFC3B
manager: dansimp
ms.reviewer:
ms.author: kenwith
author: kenwith
---

# Update-DedupStatus

## SYNOPSIS
Scans one or more specified volumes to compute fresh data deduplication savings information and returns a DeduplicationStatus object.

## SYNTAX

```
Update-DedupStatus [[-Volume] <String[]>] [-AsJob] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
```

## DESCRIPTION
The **Update-DedupStatus** cmdlet scans one or more specified volumes to compute fresh data deduplication savings information.
This cmdlet returns a DeduplicationStatus object.
For quick access to cached metadata use Get-DedupStatus.
When this cmdlet is run on multiple volumes with one cmdlet call, the analysis for each volume is done serially.

Note: On large volumes this cmdlet can run for several minutes and will always perform a rescan after the initial scan.
The default behavior is to wait for completion, regardless of the length of time required to run the scan and rescan.

To run this cmdlet, you must start Windows PowerShell® with the **Run as administrator** option.

This cmdlet returns the following metadata: 

                      
 - DedupSavedSpace: Saved space is the difference between the logical size of the optimized files and the logical size of the store (the deduplicated user data plus data deduplication metadata).
This number will change continually. 

                      
 - DedupRate: Data deduplication rate is the ratio of data deduplication saved space to the logical size of all of the files on the volume and is expressed in percentage.
This number will change continually. 

                      
 - OptimizedFilesCount: Optimized files count is the number of optimized files on the specified volume.
Note that this number will remain steady (instead of decrease) as users delete files from, or add files to, the volume-until a garbage collection job is run.
This count is most accurate after a garbage collection job runs. 

                      
 - OptimizedFilesSize: Optimized files size is the aggregate size of all optimized files on the specified volume.
Note that this number will remain steady (instead of decrease) as users delete files from, or add new files to, the volume-until a garbage collection job is run.
This number is most accurate after a garbage collection job runs. 

                      
 - InPolicyFilesCount: In policy files count is the number of files that currently qualify for optimization.
This number will stay relatively constant between optimization jobs. 

                      
 - InPolicyFilesSize: In policy files size is the aggregate size of all files that currently qualify for optimization.
This number will stay relatively constant between optimization jobs. 

                      
 - LastOptimizationTime: Last optimization time specifies the data and time when an optimization job was run last on the specified volume.
This date and time will stay constant between optimization jobs. 

                      
 - LastGarbageCollectionTime: Last garbage collection time specifies the data and time when a garbage collection job was run last on the specified volume.
This date and time will stay constant between optimization jobs. 

                      
 - LastScrubbingTime: Last scrubbing time specifies the data and time when a scrubbing job was run last on the specified volume.
This date and time will stay constant between optimization jobs.

## EXAMPLES

### 1:
```
PS C:\>
```

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

### -Volume
Specifies one or more file system volumes for which to scan and compute fresh data deduplication savings information.
Enter one or more volume IDs, drive letters (such as `D:`), or volume GUID pathnames (using the form `\\\\?\Volume{{GUID}}\\`).
Separate multiple volumes with a comma.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: Path,Name,DeviceId

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

## INPUTS

### System.String[]

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Get-DedupStatus](./Get-DedupStatus.md)

