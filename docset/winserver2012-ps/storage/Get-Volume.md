---
external help file: Storage2_Cmdlets.xml
Module Name: Storage
online version: https://docs.microsoft.com/powershell/module/storage/get-volume?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-Volume

## SYNOPSIS
Gets the specified Volume object, or all Volume objects if no filter is provided.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-Volume [[-DriveLetter] <Char[]>] [-AsJob] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_2
```
Get-Volume [-AsJob] [-CimSession <CimSession[]>] [-FileSystemLabel <String[]>] [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_3
```
Get-Volume [-AsJob] [-CimSession <CimSession[]>] [-ObjectId <String[]>] [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_4
```
Get-Volume [-AsJob] [-CimSession <CimSession[]>] [-DiskImage <CimInstance>] [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_5
```
Get-Volume [-AsJob] [-CimSession <CimSession[]>] [-Partition <CimInstance>] [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_6
```
Get-Volume [-AsJob] [-CimSession <CimSession[]>] [-Path <String[]>] [-ThrottleLimit <Int32>]
```

## DESCRIPTION
The **Get-Volume** cmdlet will return a Volume object or a set of Volume objects that match the specified criteria.

Note: Dynamic volumes are supported only by the following cmdlets: 
Repair-Volume (chkdsk), Optimize-Volume (defrag), and Format-Volume (format) on basic disks and storage spaces.

## EXAMPLES

### Example 1: Get all volumes
```
PS C:\>Get-Volume
```

This example returns all volumes on all partitions, on all disks.

### Example 2: Get the volume for a particular drive letter
```
PS C:\>Get-Volume -DriveLetter C
DriveLetter         FileSystemLabel     FileSystem          HealthStatus              SizeRemaining                Size 
-----------         ---------------     ----------          ------------              -------------                ---- 
C                                       NTFS                Healthy                        23.61 GB           465.42 GB
```

This example gets the Volume object for drive letter C.

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
Enter a computer name or a session object, such as the output of a New-CimSessionhttps://go.microsoft.com/fwlink/p/?LinkId=227967 or Get-CimSessionhttps://go.microsoft.com/fwlink/p/?LinkId=227966 cmdlet.
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

### -DiskImage
Gets the volume associated with the specified DiskImage object.
Enter a DiskImage CIM object, which is returned by the Get-DiskImage cmdlet.

```yaml
Type: CimInstance
Parameter Sets: UNNAMED_PARAMETER_SET_4
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -DriveLetter
Gets the volume(s) with the specified drive letter(s).
Separate multiple drive letters with commas.x

```yaml
Type: Char[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -FileSystemLabel
Gets the volume with the specified label.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -ObjectId
Gets the volume with the specified ObjectID.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: Id

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -Partition
Gets the volume associated with the specified Partition object.
Enter a Partition CIM object, which is returned by the Get-Partition cmdlet.

```yaml
Type: CimInstance
Parameter Sets: UNNAMED_PARAMETER_SET_5
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Path
Gets the volume with the specified path.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_6
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
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

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_DiskImage
You can pipe a DiskImage object to the **DiskImage** parameter.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_Partition
You can pipe a Partition object to the **Partition** parameter.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_Volume
You can pipe a Volume object to this cmdlet.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_Volume
This cmdlet returns one or more objects that represent the specified volume(s).

## NOTES

## RELATED LINKS

[Get-Disk](./Get-Disk.md)

[Get-Partition](./Get-Partition.md)

[Format-Volume](./Format-Volume.md)

[Optimize-Volume](./Optimize-Volume.md)

[Repair-Volume](./Repair-Volume.md)

[Set-Volume](./Set-Volume.md)

