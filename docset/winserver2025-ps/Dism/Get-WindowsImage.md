---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Dism.PowerShell.dll-Help.xml
Module Name: System.Object[]
ms.date: 12/21/2016
online version: https://learn.microsoft.com/powershell/module/dism/get-windowsimage?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WindowsImage
---

# Get-WindowsImage

## SYNOPSIS
Gets information about a Windows image in a WIM or VHD file.

## SYNTAX

### InputByFilePath
```
Get-WindowsImage -ImagePath <String> [-LogPath <String>] [-ScratchDirectory <String>] [-LogLevel <LogLevel>]
 [<CommonParameters>]
```

### InputByFilePathAndName
```
Get-WindowsImage -ImagePath <String> -Name <String> [-LogPath <String>] [-ScratchDirectory <String>]
 [-LogLevel <LogLevel>] [<CommonParameters>]
```

### InputByFilePathAndIndex
```
Get-WindowsImage -ImagePath <String> -Index <UInt32> [-LogPath <String>] [-ScratchDirectory <String>]
 [-LogLevel <LogLevel>] [<CommonParameters>]
```

### InputByMounted
```
Get-WindowsImage [-Mounted] [-LogPath <String>] [-ScratchDirectory <String>] [-LogLevel <LogLevel>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-WindowsImage** cmdlet gets information about a Windows image in a WIM or VHD file.

Use the *Mounted* parameter to get information about any Windows images that are mapped to directories on the local computer.

Use the *ImagePath* parameter to get information about images in a specific WIM or VHD file.

Use the *Index* or *Name* parameter to get detailed information about a specific image in a WIM or VHD file.
For a VHD file, the *Index* must be 1.

## EXAMPLES

### Example 1: Get information about all mounted images
```
PS C:\> Get-WindowsImage -Mounted
```

This command gets information, including mount path, about all of the Windows images mounted on the local computer.

### Example 2: Get information about a specific mounted image
```
PS C:\> Get-WindowsImage -ImagePath "c:\imagestore\install.wim" -Name Ultimate
```

This command gets detailed information about the Windows image named "Ultimate" in the install.wim file at c:\imagestore.

### Example 3: Get information about a specific image
```
PS C:\> Get-WindowsImage -ImagePath "c:\imagestore\install.vhd"
```

This command gets basic information about the Windows image in the install.vhd file at c:\imagestore.

## PARAMETERS

### -ImagePath
Specifies the location of a WIM or VHD file.

```yaml
Type: String
Parameter Sets: InputByFilePath, InputByFilePathAndName, InputByFilePathAndIndex
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

### -Mounted
Gets information, including the mount path, for all images mapped to a directories on the local computer.

```yaml
Type: SwitchParameter
Parameter Sets: InputByMounted
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the name of an image in a WIM or VHD file.

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

## OUTPUTS

### Microsoft.Dism.Commands.ImageInfoObject

### Microsoft.Dism.Commands.MountedImageInfoObject

### Microsoft.Dism.Commands.WimImageInfoObject

### Microsoft.Dism.Commands.BasicImageInfoObject

## NOTES

## RELATED LINKS

[Dismount-WindowsImage](./Dismount-WindowsImage.md)

[Mount-WindowsImage](./Mount-WindowsImage.md)

[Repair-WindowsImage](./Repair-WindowsImage.md)

[Save-WindowsImage](./Save-WindowsImage.md)

