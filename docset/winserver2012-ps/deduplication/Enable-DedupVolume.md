---
external help file: Dedup_Cmdlets.xml
online version: 
schema: 2.0.0
ms.assetid: 4A752894-524D-4A64-8483-F06A73AB0ED0
ms.reviewer:
ms.author: kenwith
author: kenwith
---

# Enable-DedupVolume

## SYNOPSIS
Enables data deduplication on one or more volumes.

## SYNTAX

```
Enable-DedupVolume [-Volume] <String[]> [-AsJob] [-CimSession <CimSession[]>] [-DataAccess]
 [-ThrottleLimit <Int32>]
```

## DESCRIPTION
The **Enable-DedupVolume** cmdlet enables data deduplication on one or more volumes .
You can use the Set-DedupVolume cmdlet to customize the data deduplication settings.
Data deduplication is disabled by default.
Data deduplication is not supported for certain volumes, such as any volume that is not a NTFS file system or any volume that is smaller than 2 GB.

## EXAMPLES

### Example 1: Enable data deduplication on volumes
```
PS C:\>Enable-DedupVolume -Volume D:,E:,F:
```

This command enables data deduplication on volumes D:, E:, and F:.

### Example 2: Enable data deduplication on a volume by using a GUID
```
PS C:\>Enable-DedupVolume -Volume "\\?\Volume{26a21bda-a627-11d7-9931-806e6f6e6963}\"
```

This command enables data deduplication for the volume that has the GUID 26a21bda-a627-11d7-9931-806e6f6e6963.

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

### -DataAccess
Indicates that data access to deduplicated files on the volume is enabled.

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

### -Volume
Specifies an array of system volumes.
Specify one or more volume IDs, drive letters (such as D:), or volume GUID pathnames (using the form \\\\?\Volume{{GUID}}\\).
Separate multiple volumes with a comma.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: Path,Name,DeviceId

Required: True
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

[Disable-DedupVolume](./Disable-DedupVolume.md)

[Get-DedupVolume](./Get-DedupVolume.md)

[Set-DedupVolume](./Set-DedupVolume.md)

