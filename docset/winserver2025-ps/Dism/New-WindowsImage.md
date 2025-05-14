---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Dism.PowerShell.dll-Help.xml
Module Name: System.Object[]
ms.date: 12/21/2016
online version: https://learn.microsoft.com/powershell/module/dism/new-windowsimage?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-WindowsImage
---

# New-WindowsImage

## SYNOPSIS
Captures an image of a drive to a new WIM file.

## SYNTAX

```
New-WindowsImage -ImagePath <String> -CapturePath <String> [-CompressionType <String>]
 [-ConfigFilePath <String>] [-Description <String>] -Name <String> [-CheckIntegrity] [-NoRpFix] [-Setbootable]
 [-Verify] [-WIMBoot] [-SupportEa] [-LogPath <String>] [-ScratchDirectory <String>] [-LogLevel <LogLevel>]
 [<CommonParameters>]
```

## DESCRIPTION
The **New-WindowsImage** cmdlet captures an image of a drive to a new WIM file.
Captured directories include all subfolders and data.
You cannot capture an empty directory.
A directory must contain at least one file.

This cmdlet does not apply to virtual hard disk (VHD) files.

## EXAMPLES

### Example 1: Capture an image of a drive for a WIM file
```
PS C:\> New-WindowsImage -ImagePath "c:\imagestore\custom.wim" -CapturePath "d:\" -Name "Drive D"
```

This command captures the Drive D image in the WIM file located on d:\ and save to the file c:\imagestore\custom.wim.

## PARAMETERS

### -CapturePath
Specifies the drive or path to the Windows operating system that is to be captured to an image file.

When the path specified is not the root folder of a drive, the captured image will inherit the parent folder security descriptors. If you are capturing an image that was previously applied, apply the original image to the root folder of the drive to ensure that the security descriptors of the new image remain the same.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

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
Specifies the type of compression used for the initial capture operation:

- **Max** = This option provides the best compression but takes more time to capture the image.
- **Fast** = This option provides faster image compression but the resulting files are larger than those compressed using the maximum (max) option.
- **None** = This option does not compress the captured image at all.

The *CompressionType* parameter does not apply when you export an image to an existing .wim file, you can only use this CompressionType when you export an image to a new .wim file.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Fast
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ConfigFilePath
Specifies the location of a configuration file that lists exclusions for image capture commands and compress commands.
For more information, see [DISM Configuration List and WimScript.ini Files](https://go.microsoft.com/fwlink/?LinkID=313768) in the TechNet Library.

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

### -Description
Specifies the description of the image to be captured.

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

### -ImagePath
Specifies the location of a WIM file.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LogLevel
Specifies the maximum output level shown in the logs.
The default log level is WarningsInfo.
The accepted values are as follows:

- Errors = Errors only
- Warnings = Errors and warnings
- WarningsInfo = Errors, warnings, and information

```yaml
Type: LogLevel
Parameter Sets: (All)
Aliases: LL
Accepted values: Errors, Warnings, WarningsInfo

Required: False
Position: Named
Default value: None
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

### -Name
Specifies the name of an image in a WIM file.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NoRpFix
Disables the reparse point tag fix.
A reparse point is a file that contains a link to another file on the file system.
If the parameter is not specified, reparse points that resolve to paths outside of the value specified by the *ImagePath* parameter will not be captured.

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

### -SupportEa
Captures extended attributes. The switch must be explicitly specified to capture extended
attributes. DISM captures extended attribute bits if they are set in the components to be
captured in the WIM image. If the bits are not set, DISM won't set them. Only the inbox components
of CAB packages and drivers will have these extended attribute bits, not the AppX package components
or Win32 application components. Extended attributes with the prefix `$Kernel.` in their name are skipped
because only user mode extended attributes are captured.

If you use DISM in Windows 10, version 1607
or later to capture extended attributes and use an earlier version of DISM to apply the image, the
operation will succeed but the extended attributes will not be set to the applied image.

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

### -Verify
Checks for errors and file duplication.
 During an apply operation, for example, using the **Add-WindowsImage** cmdlet, the size and the hash of the file being applied are checked against the image file to verify they are both equal.
 During a capture operation, for example, when using the **New-WindowsImage** cmdlet, after the file is captured into a Windows image, the file is written to a temporary file and compared on a bit-by-bit basis with the original file.

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

### -WIMBoot
Specifies that the image will be formatted to install on a Windows Image Format Boot (WIMBoot) system.

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

[Expand-WindowsImage](./Expand-WindowsImage.md)

[Export-WindowsImage](./Export-WindowsImage.md)

[Get-WindowsImage](./Get-WindowsImage.md)

[Mount-WindowsImage](./Mount-WindowsImage.md)

[Remove-WindowsImage](./Remove-WindowsImage.md)

[Repair-WindowsImage](./Repair-WindowsImage.md)

[Save-WindowsImage](./Save-WindowsImage.md)

[Split-WindowsImage](./Split-WindowsImage.md)
