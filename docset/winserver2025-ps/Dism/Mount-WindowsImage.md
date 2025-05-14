---
description: Mounts a Windows image in a WIM or VHD file to a directory on the local computer.
external help file: Microsoft.Dism.PowerShell.dll-Help.xml
Module Name: System.Object[]
ms.date: 10/06/2021
online version: https://learn.microsoft.com/powershell/module/dism/mount-windowsimage?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Mount-WindowsImage
---

# Mount-WindowsImage

## SYNOPSIS
Mounts a Windows image in a WIM or VHD file to a directory on the local computer.

## SYNTAX

### OfflineIndex
```
Mount-WindowsImage -Path <String> -ImagePath <String> -Index <UInt32> [-ReadOnly] [-Optimize] [-CheckIntegrity]
 [-SupportEa] [-LogPath <String>] [-ScratchDirectory <String>] [-LogLevel <LogLevel>] [<CommonParameters>]
```

### OfflineName
```
Mount-WindowsImage -Path <String> -ImagePath <String> -Name <String> [-ReadOnly] [-Optimize] [-CheckIntegrity]
 [-SupportEa] [-LogPath <String>] [-ScratchDirectory <String>] [-LogLevel <LogLevel>] [<CommonParameters>]
```

### Remount
```
Mount-WindowsImage -Path <String> [-Remount] [-SupportEa] [-LogPath <String>] [-ScratchDirectory <String>]
 [-LogLevel <LogLevel>] [<CommonParameters>]
```

## DESCRIPTION
The **Mount-WindowsImage** cmdlet maps a Windows image in a WIM or VHD file to the specified directory so that it is accessible for servicing.

The *Path* parameter specifies the location where you want to mount the Windows image.

The *ImagePath* parameter specifies the location of the WIM or VHD file containing the Windows image you want to mount.

Use the *Index* or *Name* parameter to specify which image in a WIM or VHD file that you want to mount.
For a VHD file, the *Index* must be 1.

The *Optimize* parameter reduces the amount of time it takes to initially mount the image.
However, processes that are ordinarily performed during a mount will instead be completed the first time that you access a directory.
As a result, there may be an increase in the time that is required to access a directory for the first time after mounting an image using the *Optimize* parameter.

The *Remount* parameter mounts an image in a WIM or VHD file that was already mounted at the specified *Path*, but has become inaccessible for servicing.

The *CheckIntegrity* parameter detects and tracks .wim file corruption.
*CheckIntegrity* stops the operation if DISM detects that the .wim file is corrupted when used with the **Mount-WindowsImage** cmdlet.

The *CheckIntegrity* parameter does not apply to virtual hard disk (VHD) files.

## EXAMPLES

### Example 1: Mount an image from the install.vhd file to a directory
```
PS C:\> Mount-WindowsImage -ImagePath "c:\imagestore\install.vhd" -Index 1 -Path "c:\offline"
```

This command mounts the Windows image contained in the install.vhd file to the c:\offline directory.

### Example 2: Mount an image at an index of a file with read-only privileges
```
PS C:\> Mount-WindowsImage -ImagePath "c:\imagestore\install.wim" -Index 2 -Path "c:\offline" -ReadOnly
```

This command mounts the Windows image at index 2 of the install.wim file to the c:\offline directory with read-only privileges.

### Example 3: Mount an image at an index of a file
```
PS C:\> Mount-WindowsImage -ImagePath "c:\imagestore\install.wim" -Index 2 -Path "c:\offline" -Optimize
```

This command mounts the Windows image at index 2 of the install.wim file to the c:\offline directory with a quicker initial mount time.
Additional operations may be slower.

### Example 4: Remounts an image previously mounted to a directory that is inaccessible
```
PS C:\> Mount-WindowsImage -Path "c:\offline" -Remount
```

This command remounts a Windows image that has already been mounted to the c:\offline directory but has become inaccessible for servicing.

### Example 5: Mount an image at an index of a file specifying logpath with checkintegrity and optimize parameters
```PowerShell
PS C:\> Mount-WindowsImage -Checkintegrity -ImagePath "c:\imagestore\install.wim" -Index 2 -Path "c:\offline" -Logpath C:\install.log -Optimize
```

This command mounts the Windows image at index 2 of the install.wim file to the c:\offline directory with Checkintegrity parameter, requesting a log file to be written and with a quicker initial mount time. Additional operations may be slower.


## PARAMETERS

### -CheckIntegrity
Detects and tracks .wim file corruption when used with the **Dismount-WindowsImage** or **Save-WindowsImage** cmdlet.
*CheckIntegrity* stops the operation if DISM detects that the .wim file is corrupted when used with the **Mount-WindowsImage** cmdlet.
The *CheckIntegrity* parameter does not apply to virtual hard disk (VHD) files.

```yaml
Type: SwitchParameter
Parameter Sets: OfflineIndex, OfflineName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ImagePath
Specifies the location of the WIM or VHD file containing the Windows image you want to mount.

```yaml
Type: String
Parameter Sets: OfflineIndex, OfflineName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Index
Specifies the index number of a Windows image in a WIM or VHD file.
For a VHD file, the *Index* must be 1.

```yaml
Type: UInt32
Parameter Sets: OfflineIndex
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
Specifies the name of an image in a WIM or VHD file.

```yaml
Type: String
Parameter Sets: OfflineName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Optimize
Reduces the amount of time it takes to initially mount the image.
However, processes that are ordinarily performed during a mount will instead be completed the first time that you access a directory.
As a result, there may be an increase in the time that is required to access a directory for the first time after mounting an image using the *Optimize* parameter.

```yaml
Type: SwitchParameter
Parameter Sets: OfflineIndex, OfflineName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Path
Specifies the location on your local computer where you want to mount the Windows image.

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

### -ReadOnly
Specifies that the image should be mounted with read-only permissions.

```yaml
Type: SwitchParameter
Parameter Sets: OfflineIndex, OfflineName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Remount
Mounts an image in a WIM or VHD file that was already mounted at the specified *Path*, but has become inaccessible for servicing.

```yaml
Type: SwitchParameter
Parameter Sets: Remount
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

Applies an image with extended attributes.

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

### Microsoft.Dism.Commands.ImageInfoObject

## OUTPUTS

### Microsoft.Dism.Commands.ImageObject

## NOTES

## RELATED LINKS

[Dismount-WindowsImage](./Dismount-WindowsImage.md)

[Save-WindowsImage](./Save-WindowsImage.md)

[Get-WindowsImage](./Get-WindowsImage.md)

[Repair-WindowsImage](./Repair-WindowsImage.md)
