---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Dism.PowerShell.dll-Help.xml
Module Name: System.Object[]
ms.date: 08/25/2021
online version: https://learn.microsoft.com/powershell/module/dism/add-windowsimage?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-WindowsImage
---

# Add-WindowsImage

## SYNOPSIS
Adds an additional image to an existing image (.wim) file.

## SYNTAX

```
Add-WindowsImage -ImagePath <String> -CapturePath <String> [-ConfigFilePath <String>] [-Description <String>]
 -Name <String> [-CheckIntegrity] [-NoRpFix] [-Setbootable] [-Verify] [-WIMBoot] [-SupportEa]
 [-LogPath <String>] [-ScratchDirectory <String>] [-LogLevel <LogLevel>] [<CommonParameters>]
```

## DESCRIPTION
The **Add-WindowsImage** cmdlet adds an additional image to an existing image (.wim) file.
**Add-WindowsImage** compares new files to the resources in the existing .wim file, specified by the *Name* parameter and the *ImagePath* parameter, and stores only a single copy of each unique file so that each file is only captured once.
The .wim file can have only one assigned compression type.
Therefore, you can only append files with the same compression type.

The **Add-WindowsImage** cmdlet does not apply to virtual hard disk (VHD) files.

It's important to note that you'll need to ensure you have enough disk space before you run **Add-WindowsImage**.
If you run out of disk space while the image is being appended, you might corrupt the .wim file.

## EXAMPLES

### Example 1: Add files to an image
```
PS C:\> Add-WindowsImage -ImagePath "C:\imagestore\custom.wim" -CapturePath d:\ -Name "Drive D"
```

This command adds files from d:\"Drive D" to the existing image at c:\imagestore\custom.wim.

## PARAMETERS

### -CapturePath
Specifies the path to the location of the new files that will be compared to the resources in the existing .wim file.

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

### -ConfigFilePath
Specifies the location of a configuration file that lists exclusions for image capture and compress commands.
For more information, see [DISM Configuration List and WimScript.ini Files](https://go.microsoft.com/fwlink/?LinkID=313768).

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
Specifies the location of the WIM file containing the Windows image you want to compare against the new files.

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
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SupportEa
Appends an image with extended attributes.

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
 During a capture operation, for example, when using the **New-WindowsImage** cmdlet, after the files is captured into a Windows image, the file is written to a temporary file and compared on a bit-by-bit basis with the original file.

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
Specifies that the offline image to be added will be formatted to install on a Windows Image Format Boot (WIMBoot) system.

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

[New-WindowsImage](./New-WindowsImage.md)

[Remove-WindowsImage](./Remove-WindowsImage.md)

[Repair-WindowsImage](./Repair-WindowsImage.md)

[Save-WindowsImage](./Save-WindowsImage.md)

[Split-WindowsImage](./Split-WindowsImage.md)

