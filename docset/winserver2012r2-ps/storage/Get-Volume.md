---
external help file: Volume.cdxml-help.xml
Module Name: Storage
ms.date: 10/29/2017
online version: https://learn.microsoft.com/powershell/module/storage/get-volume?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Volume
---

# Get-Volume

## SYNOPSIS
Gets the specified Volume object, or all Volume objects if no filter is provided.

## SYNTAX

### ByDriveLetter (Default)
```
Get-Volume [[-DriveLetter] <Char[]>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ById
```
Get-Volume [-ObjectId <String[]>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByPaths
```
Get-Volume [-Path <String[]>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByLabel
```
Get-Volume [-FileSystemLabel <String[]>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByPartition
```
Get-Volume [-Partition <CimInstance>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByDiskImage
```
Get-Volume [-DiskImage <CimInstance>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByFilePath
```
Get-Volume [-FilePath <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
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

### -DiskImage
Gets the volume associated with the specified DiskImage object.
Enter a DiskImage CIM object, which is returned by the Get-DiskImage cmdlet.

```yaml
Type: CimInstance
Parameter Sets: ByDiskImage
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
Parameter Sets: ByDriveLetter
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -FilePath
Specifies the full path of a file.
The cmdlet gets the volume for the file path that you specify.

```yaml
Type: String
Parameter Sets: ByFilePath
Aliases: FullName

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -FileSystemLabel
Gets the volume with the specified label.

```yaml
Type: String[]
Parameter Sets: ByLabel
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ObjectId
Gets the volume with the specified ObjectID.

```yaml
Type: String[]
Parameter Sets: ById
Aliases: Id

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Partition
Gets the volume associated with the specified Partition object.
Enter a Partition CIM object, which is returned by the Get-Partition cmdlet.

```yaml
Type: CimInstance
Parameter Sets: ByPartition
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
Parameter Sets: ByPaths
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_DiskImage
You can use the pipeline operator to pass a DiskImage object to the **DiskImage** parameter.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_Partition
You can use the pipeline operator to pass a Partition object to the **Partition** parameter.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_Volume
You can use the pipeline operator to pass a Volume object to the **ObjectId** parameter.

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

