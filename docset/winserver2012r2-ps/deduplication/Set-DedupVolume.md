---
external help file: DedupVolume.cdxml-help.xml
Module Name: Deduplication
ms.date: 10/30/2017
online version: https://docs.microsoft.com/powershell/module/deduplication/set-dedupvolume?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-DedupVolume
---

# Set-DedupVolume

## SYNOPSIS
Changes data deduplication settings on one or more volumes.

## SYNTAX

### ByVolume (Default)
```powershell
Set-DedupVolume [-Volume] <String[]> [-OptimizeInUseFiles] [-OptimizePartialFiles] [-NoCompress <Boolean>]
 [-Verify <Boolean>] [-MinimumFileAgeDays <UInt32>] [-MinimumFileSize <UInt32>]
 [-ChunkRedundancyThreshold <UInt32>] [-ExcludeFolder <String[]>] [-ExcludeFileType <String[]>]
 [-ExcludeFileTypeDefault <String[]>] [-NoCompressionFileType <String[]>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [<CommonParameters>]
```

### InputObject (cdxml)
```powershell
Set-DedupVolume -InputObject <CimInstance[]> [-OptimizeInUseFiles] [-OptimizePartialFiles]
 [-NoCompress <Boolean>] [-Verify <Boolean>] [-MinimumFileAgeDays <UInt32>] [-MinimumFileSize <UInt32>]
 [-ChunkRedundancyThreshold <UInt32>] [-ExcludeFolder <String[]>] [-ExcludeFileType <String[]>]
 [-ExcludeFileTypeDefault <String[]>] [-NoCompressionFileType <String[]>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [<CommonParameters>]
```

## DESCRIPTION
The **Set-DedupVolume** cmdlet changes data deduplication settings on one or more volumes.

## EXAMPLES

### Example 1: Set the exclude folders on a volume
```powershell
PS C:\>Set-DedupVolume -Volume F: -ExcludeFolder F:\temp,F:\SQL
```

This command sets the root folders under which all files are skipped during data deduplication.
The *ExcludeFolder* parameter specifies that the data deduplication engine processes the files in all of the folders on volume F: except for files in the Temp folder and the SQL folder.

### Example 2: Set the minimum file age on a volume
```powershell
PS C:\>Set-DedupVolume -Volume E: -MinimumFileAgeDays 10
```

This command sets the number of days since users have accessed a file before the deduplication engine optimizes the file.
The *MinimumFileAgeDays* parameter specifies that the data deduplication engine processes the files in all of the folders on volume E: that were not accessed in the last 10 days.

### Example 3: Set the chunk redundancy threshold on a volume
```powershell
PS C:\>Set-DedupVolume -Volume D: -MinimumFileAgeDays 15 -ChunkRedundancyThreshold 50
```

This command sets the number of identical chunks of data that the deduplication engine encounters during deduplication before the server creates a redundant copy of the data chunk.
The *MinimumFileAgeDays* parameter specifies that the data deduplication engine processes the files in all of the folders on volume D: that were not accessed in the last 15 days.
The *ChunkRedundancyThreshold* parameter specifies that if the data deduplication engine discovers 50 chunks of identical data, it makes one redundant copy as a safeguard.

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to complete. 

The cmdlet immediately returns an object that represents the job and then displays the command prompt. 
You can continue to work in the session while the job completes. 
To manage the job, use the `*-Job` cmdlets. 
To get the job results, use the [Receive-Job](https://go.microsoft.com/fwlink/?LinkID=113372) cmdlet. 

For more information about Windows PowerShell background jobs, see [about_Jobs](https://go.microsoft.com/fwlink/?LinkID=113251).

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

### -ChunkRedundancyThreshold
Specifies the number of identical chunks of data that the deduplication engine encounters before the server creates a redundant copy of the data chunk.
This increases the reliability of the server by adding redundancy to the most referenced chunks of data.

Deduplication detects corruptions and the deduplication scrubbing job restores the corrupted chunks from a redundant copy, if it is available.
The default value is 100.
The minimum value that you can set is 20.
A low value for the *ChunkRedundancyThreshold* parameter reduces the effectiveness of data deduplication by creating more redundant copies of a chunk, and consumes more memory and disk space.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CimSession
Enter a computer name or a session object, such as the output of a [New-CimSession](https://docs.microsoft.com/powershell/module/cimcmdlets/new-cimsession) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
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

### -ExcludeFileType
Specifies an array of extension types that the deduplication engine excludes from data deduplication and optimization.
Specify comma-separated values that are not preceded with a period (.).
When you change this setting, you override the existing values.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExcludeFileTypeDefault
Specifies an array of file extension types, as strings, that the server does not optimize.

The **Enable-DedupVolume** cmdlet modifies this behavior, depending on the value of the *UsageType* parameter.
If you use the current parameter to modify this behavior, and then run Enable-DedupVolume again, that cmdlet overrides your changes.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExcludeFolder
Specifies an array of names of root folders under which all files are skipped during data deduplication.
Full paths are accepted, however mount points are ignored since the mount point can change after configuration.
When you change this setting, you override the existing values.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Specifies the input to this cmdlet.
You can use this parameter, or you can pipe the input to this cmdlet.

```yaml
Type: CimInstance[]
Parameter Sets: InputObject (cdxml)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -MinimumFileAgeDays
Specifies a number of days.
The deduplication engine optimizes files that users have not accessed in the number of days that you specify.
If the last access time is not available, then the deduplication engine uses the last modified time.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: MinimumFileAge

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MinimumFileSize
Specifies the minimum size threshold, in bytes, for files that are optimized.
The deduplication engine does not optimize files that do not meet the minimum threshold.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoCompress
Indicates whether or not the server compresses data after deduplication.
Compression uses more processor cycles but provides additional space savings.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoCompressionFileType
Specifies an array of file types that the deduplication engine excludes from compression.
These file types are deduplicated but not compressed, typically because the file format is already compressed.
Specify comma-separated values that are not preceded with a period (.).
When you change this setting, you override the existing values.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: Video files, previously compressed files, all Microsoft Office 2007 files. These include, but are not limited to: aac|aif|aiff|asf|asx|au|avi|flac|jpeg|m3u|mid|midi|mov|mp1|mp2|mp3|mp4|mpa|mpe|mpeg|mpeg2|mpeg3|mpg|ogg|qt|qtw|ram|rm|rmi|rmvb|snd|swf|vob|wav|wax|wma|wmv|wvx|accdb|accde|accdr|accdt|docm|docx|dotm|dotx|pptm|potm|potx|ppam|ppsx|pptx|sldx|sldm|thmx|xlsx|xlsm|xltx|xltm|xlsb|xlam|xll|ace|arc|arj|bhx|b2|cab|gz|gzip|hpk|hqx|jar|lha|lzh|lzx|pak|pit|rar|sea|sit|sqz|tgz|uu|uue|z|zip|zoo
Accept pipeline input: False
Accept wildcard characters: False
```

### -OptimizeInUseFiles
Indicates that the server attempts to optimize currently open files.
After specifying this parameter, the server may wait up to 15 mines before it attempts to optimize open files.

**Enable-DedupVolume** modifies this behavior, depending on the value of the *UsageType* parameter.
If you use the current parameter to modify this behavior, and then run **Enable-DedupVolume** again, that cmdlet overrides your changes.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -OptimizePartialFiles
Indicates that the server optimizes all files, including portions of files that are old enough, according to the value of the *MinimumFileAgeDays* parameter.

**Enable-DedupVolume** modifies this behavior, depending on the value of the *UsageType* parameter.
If you use the current parameter to modify this behavior, and then run **Enable-DedupVolume** again, that cmdlet overrides your changes.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru
Returns an object representing the item with which you are working.
By default, this cmdlet does not generate any output.

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

### -Verify
Indicates whether or not the deduplication engine performs a byte-for-byte verification for each duplicate chunk that optimization creates, rather than relying on a cryptographically strong hash.
We do not recommend that you use this parameter.
Setting this parameter to $True can degrade optimization performance.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Volume
Specifies an array of system volumes.
Specify one or more volume IDs, drive letters, or volume GUID paths.
For drive letters, use the format D:.
For volume GUID paths, use the format \\\\?\Volume{{GUID}}\.
Separate multiple volumes with a comma.
```yaml
Type: String[]
Parameter Sets: ByVolume
Aliases: Path, Name

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String[]

### Microsoft.Management.Infrastructure.CimInstance
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Deduplication/MSFT_DedupVolume

## NOTES

## RELATED LINKS

[Disable-DedupVolume](./Disable-DedupVolume.md)

[Enable-DedupVolume](./Enable-DedupVolume.md)

[Get-DedupVolume](./Get-DedupVolume.md)

