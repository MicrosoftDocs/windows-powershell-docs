---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Dism.PowerShell.dll-Help.xml
Module Name: System.Object[]
ms.date: 12/21/2016
online version: https://learn.microsoft.com/powershell/module/dism/dismount-windowsimage?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Dismount-WindowsImage
---

# Dismount-WindowsImage

## SYNOPSIS
Dismounts a Windows image from the directory it is mapped to.

## SYNTAX

### DismountDiscard
```
Dismount-WindowsImage -Path <String> [-Discard] [-LogPath <String>] [-ScratchDirectory <String>]
 [-LogLevel <LogLevel>] [<CommonParameters>]
```

### DismountSave
```
Dismount-WindowsImage -Path <String> [-Save] [-CheckIntegrity] [-Append] [-LogPath <String>]
 [-ScratchDirectory <String>] [-LogLevel <LogLevel>] [<CommonParameters>]
```

## DESCRIPTION
The **Dismount-WindowsImage** cmdlet either saves or discards the changes to a Windows image and then dismounts the image.

The *Path* parameter specifies the location of the mounted Windows image.

The *Append* parameter specifies the location of an existing .wim file to add the Windows image to when you dismount it instead of overwriting the existing image.

The *CheckIntegrity* parameter detects and tracks .wim file corruption.
CheckIntegrity stops the operation if DISM detects that the .wim file is corrupted when used with the **Mount-WindowsImage** cmdlet.

The *CheckIntegrity* and *Append* parameters do not apply to virtual hard disk (VHD) files.

## EXAMPLES

### Example 1: Dismount an operating system image
```
PS C:\> Dismount-WindowsImage -Path "c:\offline" -Save
```

This command dismounts the Windows Image mapped to c:\offline and saves any changes that were made while servicing the image.

## PARAMETERS

### -Append
Specifies the location of an existing .wim file to add the Windows image to when you dismount it instead of overwriting the existing image.

```yaml
Type: SwitchParameter
Parameter Sets: DismountSave
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CheckIntegrity
Detects and tracks .wim file corruption.
*CheckIntegrity* stops the operation if DISM detects that the .wim file is corrupted when used with the **Mount-WindowsImage** cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: DismountSave
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Discard
Discards the changes to a Windows image.

```yaml
Type: SwitchParameter
Parameter Sets: DismountDiscard
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

### -Path
Specifies the full path to the root directory of the offline Windows image that you will service.
If the directory named Windows is not a subdirectory of the root directory, *WindowsDirectory* must be specified.

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

### -Save
Saves the changes to a Windows image.

```yaml
Type: SwitchParameter
Parameter Sets: DismountSave
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String[]

### Microsoft.Dism.Commands.ImageObject

### Microsoft.Dism.Commands.MountedImageInfoObject

### Microsoft.Dism.Commands.ImageInfoObject

## OUTPUTS

### Microsoft.Dism.Commands.BaseDismObject

## NOTES

## RELATED LINKS

[Save-WindowsImage](./Save-WindowsImage.md)

[Repair-WindowsImage](./Repair-WindowsImage.md)

[Mount-WindowsImage](./Mount-WindowsImage.md)

[Get-WindowsImage](./Get-WindowsImage.md)

