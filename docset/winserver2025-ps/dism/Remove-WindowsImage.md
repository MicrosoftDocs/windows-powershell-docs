---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Dism.PowerShell.dll-Help.xml
Module Name: System.Object[]
ms.date: 12/21/2016
online version: https://learn.microsoft.com/powershell/module/dism/remove-windowsimage?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-WindowsImage
---

# Remove-WindowsImage

## SYNOPSIS
Deletes the specified volume image from a WIM file that has multiple volume images.

## SYNTAX

### InputByFilePathAndName
```
Remove-WindowsImage -ImagePath <String> -Name <String> [-CheckIntegrity] [-LogPath <String>]
 [-ScratchDirectory <String>] [-LogLevel <LogLevel>] [<CommonParameters>]
```

### InputByFilePathAndIndex
```
Remove-WindowsImage -ImagePath <String> -Index <UInt32> [-CheckIntegrity] [-LogPath <String>]
 [-ScratchDirectory <String>] [-LogLevel <LogLevel>] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-WindowsImage** cmdlet deletes the specified volume image from a WIM file that has multiple volume images.
This cmdlet deletes only the metadata entries and XML entries.
It does not delete the stream data and does not optimize the WIM file.

This command-line option does not apply to virtual hard disk (VHD) files.

## EXAMPLES

### Example 1: Remove the first image from a WIM file
```
PS C:\> Remove-WindowsImage -ImagePath "c:\imagestore\custom.wim" -Index 1 -CheckIntegrity
```

This command removes the first image in c:\imagestore\custom.wim.

### Example 2: Remove an image from a WIM file by name
```
PS C:\> Remove-WindowsImage -ImagePath "c:\imagestore\custom.wim" -Name "Starter" -CheckIntegrity
```

This command removes the image named Starter that is located in c:\imagestore\custom.wim.

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

### -Index
Specifies the index number of a Windows image in a WIM or VHD file.
For a VHD file, the Index must be 1.

```yaml
Type: UInt32
Parameter Sets: InputByFilePathAndIndex
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
Parameter Sets: InputByFilePathAndName
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

### Microsoft.Dism.Commands.ImageObjectWithState

## OUTPUTS

### Microsoft.Dism.Commands.ImageObject

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

[Save-WindowsImage](./Save-WindowsImage.md)

[Split-WindowsImage](./Split-WindowsImage.md)

