---
external help file: Dedup_Cmdlets.xml
online version: 
schema: 2.0.0
ms.assetid: B95430BE-3433-4A31-9442-EDCE96C3DB89
ms.reviewer:
ms.author: kenwith
author: kenwith
---

# Get-DedupVolume

## SYNOPSIS
Returns a DeduplicationVolume object for each volume that has data deduplication metadata.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-DedupVolume [-AsJob] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-VolumeId <String[]>]
```

### UNNAMED_PARAMETER_SET_2
```
Get-DedupVolume [[-Volume] <String[]>] [-AsJob] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
```

## DESCRIPTION
The **Get-DedupVolume** cmdlet returns a DeduplicationVolume object for each volume that has data deduplication metadata (in either the enabled or disabled state).
In a cluster, this cmdlet returns a DeduplicationVolume object only for volumes currently mounted by the managed node (whether the volumes are local or clustered volumes).

## EXAMPLES

### Example 1
```
PS C:\>Get-DedupVolume -Volume E:
```

This example returns the data deduplication settings for volume E.

### Example 2
```
PS C:\>Get-DedupVolume -Volume "\\?\Volume{26a21bda-a627-11d7-9931-806e6f6e6963}\"
```

This example returns the data deduplication settings for the volume with the specified GUID.

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
Specifies one or more file system volumes for which to return data deduplication metadata, or in the case of a cluster, volumes with data deduplication metadata currently mounted by the managed node.
Enter one or more volume IDs, drive letters (such as `D:`), or volume GUID pathnames (using the form `\\\\?\Volume{{GUID}}\\`).
Separate multiple volumes with a comma.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VolumeId
Specifies a string that uniquely identifies the volume on which to return data deduplication metadata.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: ObjectId,Id,DeviceId

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

## INPUTS

### System.String[]

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Deduplication/MSFT_DedupVolume
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Disable-DedupVolume](./Disable-DedupVolume.md)

[Enable-DedupVolume](./Enable-DedupVolume.md)

[Set-DedupVolume](./Set-DedupVolume.md)

