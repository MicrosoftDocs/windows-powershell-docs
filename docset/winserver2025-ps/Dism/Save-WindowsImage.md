---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Dism.PowerShell.dll-Help.xml
Module Name: System.Object[]
ms.date: 10/06/2021
online version: https://learn.microsoft.com/powershell/module/dism/save-windowsimage?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Save-WindowsImage
---

# Save-WindowsImage

## SYNOPSIS
Applies changes made to a mounted image to its WIM or VHD file.

## SYNTAX

```
Save-WindowsImage -Path <String> [-CheckIntegrity] [-Append] [-SupportEa] [-LogPath <String>]
 [-ScratchDirectory <String>] [-LogLevel <LogLevel>] [<CommonParameters>]
```

## DESCRIPTION
The **Save-WindowsImage** cmdlet applies the servicing changes made to a mounted image to its WIM or VHD file without unmounting it.

The *Path* parameter specifies the location of the mounted Windows image.

The *Append* parameter specifies the location of an existing .wim file to add the Windows image to when you save it.

The *CheckIntegrity* parameter detects and tracks .wim file corruption.
*CheckIntegrity* stops the operation if DISM detects that the .wim file is corrupted when used with the **Mount-WindowsImage** cmdlet.
The *CheckIntegrity* parameter does not apply to virtual hard disk (VHD) files.

## EXAMPLES

### Example 1: Save servicing changes made to a mounted image
```
PS C:\> Save-WindowsImage -Path "c:\offline"
```

This command saves the servicing changes made to the Windows image mounted to c:\offline.
It does not unmounts the image.

## PARAMETERS

### -Append
Indicates that this cmdlet specifies the location of an existing .wim file to add the Windows image to when you save it.

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

### -CheckIntegrity
Indicates that this cmdlet detects and tracks .wim file corruption.
*CheckIntegrity* stops the operation if DISM detects that the .wim file is corrupted when used with the **Mount-WindowsImage** cmdlet.
The *CheckIntegrity* parameter does not apply to virtual hard disk (VHD) files.

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

### -Path
Specifies the full path to the root directory of the offline Windows image that you want to save.

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

### -SupportEa
Captures extended attributes.

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

### Microsoft.Dism.Commands.ImageObject

## NOTES

## RELATED LINKS

[Mount-WindowsImage](./Mount-WindowsImage.md)

[Dismount-WindowsImage](./Dismount-WindowsImage.md)

[Get-WindowsImage](./Get-WindowsImage.md)

[Repair-WindowsImage](./Repair-WindowsImage.md)

