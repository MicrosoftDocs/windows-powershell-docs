---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Dism.PowerShell.dll-Help.xml
Module Name: System.Object[]
ms.date: 12/21/2016
online version: https://learn.microsoft.com/powershell/module/dism/export-windowsimage?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Export-WindowsImage
---

# Export-WindowsImage

## SYNOPSIS
Exports a copy of the specified image to another image file.

## SYNTAX

### InputByFilePathAndName
```
Export-WindowsImage [-CheckIntegrity] [-CompressionType <String>] -DestinationImagePath <String>
 [-DestinationName <String>] [-Setbootable] -SourceImagePath <String> -SourceName <String>
 [-SplitImageFilePattern <String>] [-WIMBoot] [-LogPath <String>] [-ScratchDirectory <String>]
 [-LogLevel <LogLevel>] [<CommonParameters>]
```

### InputByFilePathAndIndex
```
Export-WindowsImage [-CheckIntegrity] [-CompressionType <String>] -DestinationImagePath <String>
 [-DestinationName <String>] [-Setbootable] -SourceImagePath <String> -SourceIndex <UInt32>
 [-SplitImageFilePattern <String>] [-WIMBoot] [-LogPath <String>] [-ScratchDirectory <String>]
 [-LogLevel <LogLevel>] [<CommonParameters>]
```

## DESCRIPTION
The **Export-WindowsImage** cmdlet exports a copy of the specified image to another image file.
The source and destination files must use the same compression type.

You can also optimize an image by exporting to a new image file with **Export-WindowsImage**.
When you modify an image, DISM stores additional resource files that increase the overall size of the image.
Exporting the image will remove unnecessary resource files.

This cmdlet does not apply to virtual hard disk (VHD) files.

## EXAMPLES

### Example 1: Export an image
```
PS C:\> Export-WindowsImage -SourceImagePath C:\imagestore\custom.wim -SourceIndex 1 -DestinationImagePath c:\imagestore\export.wim -DestinationName "Exported Image"
```

This command exports the image at Index 1 of the file C:\imagestore\custom.wim to the file c:\imagestore\export.wim with the name Exported Image.

## PARAMETERS

### -CheckIntegrity
Detects and tracks .wim file corruption when used with the **Add-WindowsImage**, **Dismount-WindowsImage**, or **Save-WindowsImage** cmdlet.
CheckIntegrity stops the operation if DISM detects that the .wim file is corrupted when used with the **Expand-WindowsImage** or **Mount-WindowsImage** cmdlet.

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

### -CompressionType
Specifies the type of compression used for the initial capture operation. Acceptable values are:

- **"max" or "maximum":** Provides the high compression, but takes more time to capture the image
- **"fast:"** Provides faster image compression, but the resulting files are larger than those compressed by using the maximum option.
- **"none":** No compression is used at all. This is the default.

> [!NOTE]
> This cmdlet does not support the "recovery" compression type. Use `dism.exe` instead.

the *CompressionType* parameter does not apply when you export an image to an existing .wim file, you can only use this CompressionType when you export an image to a new .wim file.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: "none"
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DestinationImagePath
Specifies the location of the exported image file.

```yaml
Type: String
Parameter Sets: (All)
Aliases: DIP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DestinationName
Specifies the name of the exported image in the exported image file.

```yaml
Type: String
Parameter Sets: (All)
Aliases: DN

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LogLevel
Specifies the maximum output level shown in the logs.
The default log level is 3.
The accepted values are as follows:
- 1 = Errors only
- 2 = Errors and warnings
- 3 = Errors, warnings, and information
- 4 = All of the information listed previously, plus debug output

```yaml
Type: LogLevel
Parameter Sets: (All)
Aliases: LL
Accepted values: Errors, Warnings, WarningsInfo

Required: False
Position: Named
Default value: 3
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LogPath
Specifies the full path and file name to log to.
If not set, the default is `%WINDIR%\Logs\Dism\dism.log`.
In Windows PE, the default directory is the RAMDISK scratch space which can be as low as 32 MB.
The log file will automatically be archived.
The archived log file will be saved with .bak appended to the file name and a new log file will be generated.
Each time the log file is archived the .bak file will be overwritten.
When using a network share that is not joined to a domain, use the net use command together with domain credentials to set access permissions before you set the log path for the DISM log.

```yaml
Type: String
Parameter Sets: (All)
Aliases: LP

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ScratchDirectory
Specifies a temporary directory that will be used when extracting files for use during servicing.
The directory must exist locally.
If not specified, the `\Windows\%Temp%` directory will be used, with a subdirectory name of a randomly generated hexadecimal value for each run of DISM.
Items in the scratch directory are deleted after each operation.
You should not use a network share location as a scratch directory to expand a package (.cab or .msu file) for installation.
The directory used for extracting files for temporary usage during servicing should be a local directory.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Setbootable
Marks a volume image as being a bootable image.
This argument is available only for Windows PE images.
Only one volume image can be marked as bootable in a .wim file.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: SB

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SourceImagePath
Specifies the location of the source image file. Must be used in conjunction with `-SourceIndex` or `-SourceName`. If the source file is a SWM file, `-SplitImageFilePattern` is also required.

```yaml
Type: String
Parameter Sets: (All)
Aliases: SIP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SourceIndex
Specifies the index number of a Windows image in a WIM or VHD file.
For a VHD file, the Index must be 1.

```yaml
Type: UInt32
Parameter Sets: InputByFilePathAndIndex
Aliases: SI

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SourceName
Specifies the name of the source image in the source image file.

```yaml
Type: String
Parameter Sets: InputByFilePathAndName
Aliases: SN

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SplitImageFilePattern
Specifies the location and name of the base split image file.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -WIMBoot
Specifies that the image will be formatted to install on a Windows image file boot (WIMBoot) system.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String[]

### Microsoft.Dism.Commands.ImageObject

### Microsoft.Dism.Commands.ImageObjectWithState

## OUTPUTS

### Microsoft.Dism.Commands.OfflineImageObject

## NOTES

## RELATED LINKS

[Dismount-WindowsImage](./Dismount-WindowsImage.md)

[Export-WindowsImage](./Export-WindowsImage.md)

[Get-WindowsImage](./Get-WindowsImage.md)

[Mount-WindowsImage](./Mount-WindowsImage.md)

[New-WindowsImage](./New-WindowsImage.md)

[Remove-WindowsImage](./Remove-WindowsImage.md)

[Repair-WindowsImage](./Repair-WindowsImage.md)

[Save-WindowsImage](./Save-WindowsImage.md)

[Split-WindowsImage](./Split-WindowsImage.md)

