---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Dism.PowerShell.dll-Help.xml
Module Name: System.Object[]
ms.date: 12/21/2016
online version: https://learn.microsoft.com/powershell/module/dism/split-windowsimage?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Split-WindowsImage
---

# Split-WindowsImage

## SYNOPSIS
Splits an existing .wim file into multiple read-only split .wim files.

## SYNTAX

```
Split-WindowsImage -ImagePath <String> -SplitImagePath <String> -FileSize <UInt64> [-CheckIntegrity]
 [-LogPath <String>] [-ScratchDirectory <String>] [-LogLevel <LogLevel>] [<CommonParameters>]
```

## DESCRIPTION
The **Split-WindowsImage** cmdlet creates the .swm files in the specified directory, naming each file the same as the specified path_to_swm, but with an appended number.
For example, if you set path_to_swm as `c:\Data.swm`, this option creates a Data.swm file, a Data2.swm file, a Data3.swm file, and so on, defining each portion of the split .wim file and saving it to the C:\ directory.

If a single file is larger than the value specified in the *FileSize* parameter, one of the split .swm files that results will be larger than the value specified in the *FileSize* parameter, in order to accommodate the large file.

This cmdlet does not apply to virtual hard disk (VHD) files.

## EXAMPLES

### Example 1: Split a .wim file
```
PS C:\> Split-WindowsImage -ImagePath "c:\imagestore\install.wim" -SplitImagePath "c:\imagestore\splitfiles\split.swm" -FileSize 1024 -CheckIntegrity
```

This command uses the image from c:\imagestore\install.wim to create a split.swm file, a split2.swm file, a split3.swm file, and so on, defining each portion of the split .wim file with a maximum size of 1024 MB and saving it to the C:\ imagestore\splitfiles\ directory.

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

### -FileSize
Specifies the maximum size in megabytes (MB) for each created .swm file.

```yaml
Type: UInt64
Parameter Sets: (All)
Aliases:

Required: True
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

### -SplitImagePath
Specifies the location and the base split image file name.

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

[Add-WindowsImage](./Add-WindowsImage.md)

[Dismount-WindowsImage](./Dismount-WindowsImage.md)

[Expand-WindowsImage](./Expand-WindowsImage.md)

[Export-WindowsImage](./Export-WindowsImage.md)

[Get-WindowsImage](./Get-WindowsImage.md)

[Mount-WindowsImage](./Mount-WindowsImage.md)

[New-WindowsImage](./New-WindowsImage.md)

[Repair-WindowsImage](./Repair-WindowsImage.md)

[Remove-WindowsImage](./Remove-WindowsImage.md)

[Save-WindowsImage](./Save-WindowsImage.md)

