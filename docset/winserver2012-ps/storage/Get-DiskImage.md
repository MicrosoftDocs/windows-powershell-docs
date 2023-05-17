---
external help file: Storage2_Cmdlets.xml
Module Name: Storage
online version: https://learn.microsoft.com/powershell/module/storage/get-diskimage?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-DiskImage

## SYNOPSIS
Gets one or more disk image objects (virtual hard disk or ISO).

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-DiskImage [-ImagePath] <String[]> [-AsJob] [-CimSession <CimSession[]>] [-StorageType <StorageType>]
 [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_2
```
Get-DiskImage [-AsJob] [-CimSession <CimSession[]>] [-StorageType <StorageType>] [-ThrottleLimit <Int32>]
 [-Volume <CimInstance>]
```

### UNNAMED_PARAMETER_SET_3
```
Get-DiskImage [-AsJob] [-CimSession <CimSession[]>] [-StorageType <StorageType>] [-ThrottleLimit <Int32>]
 -DevicePath <String[]>
```

## DESCRIPTION
The **Get-DiskImage** cmdlet gets the objects associated with one or more disk images (virtual hard disk or ISO).
This cmdlet requires either the full image path of the ISO or VHD file, or the device path.

This cmdlet reports whether the specified ISO or VHD file is currently attached.

## EXAMPLES

### Example 1: Get a disk image by path
```
PS C:\>Get-DiskImage -ImagePath "E:\ISO-Files\My US Visit Fall 2010 Pictures.iso"
```

This example gets an ISO disk image specified by path and displays information about the disk image.

### Example 2: Get a disk image by device path
```
PS C:\>Get-DiskImage -DevicePath \\.\CDROM1
```

This example gets an ISO disk image specified by device path and displays information about the disk image.

### Example 3: Get the drive letter associated with a mounted ISO
```
PS C:\>Get-DiskImage -DevicePath \\.\CDROM1 | Get-Volume
```

This example displays the drive letter associated with an ISO file.

### Example 4: Get the drive letter associated with a mounted VHD
```
PS C:\>Get-DiskImage -ImagePath E:\vhd1.vhdx | Get-Disk | Get-Partition | Get-Volume
DriveLetter       FileSystemLabel   FileSystem        DriveType         HealthStatus        SizeRemaining             Size

-----------       ---------------   ----------        ---------         ------------        -------------             ----

F                 New Volume        NTFS              Fixed             Healthy                  19.27 GB         19.87 GB
```

This example displays one or more drive letters associated with volumes in a VHD file.

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

### -DevicePath
Specifies the device path of the ISO or VHD file.
You cannot use this parameter with the **ImagePath** parameter.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ImagePath
Specifies the path of the ISO or VHD file.
You cannot use this parameter with the **DevicePath** parameter.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue, ByPropertyName)
Accept wildcard characters: False
```

### -StorageType
Specifies the type of a disk image: ISO, VHD, VHDx, or Unknown.
If the StorageType parameter is not specified or the Unknown type is provided, the storage type is determined by file extension.

```yaml
Type: StorageType
Parameter Sets: (All)
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

### -Volume
Gets the disk image associated with the specified Volume object.
Enter a Volume CIM object, which can be obtained by using the Get-Volume cmdlet.

```yaml
Type: CimInstance
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_Volume
You can pipe a Volume object to the **Volume** parameter.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_DiskImage
This cmdlet returns an object that represents the specified disk image.

## NOTES

## RELATED LINKS

[Dismount-DiskImage](./Dismount-DiskImage.md)

[Get-Disk](./Get-Disk.md)

[Get-Partition](./Get-Partition.md)

[Get-Volume](./Get-Volume.md)

[Mount-DiskImage](./Mount-DiskImage.md)

