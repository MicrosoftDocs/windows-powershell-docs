---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Dism.PowerShell.dll-Help.xml
Module Name: System.Object[]
ms.date: 12/21/2016
online version: https://learn.microsoft.com/powershell/module/dism/repair-windowsimage?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Repair-WindowsImage
---

# Repair-WindowsImage

## SYNOPSIS
Repairs a Windows image in a WIM or VHD file.

## SYNTAX

### Offline
```
Repair-WindowsImage [-CheckHealth] [-ScanHealth] [-RestoreHealth] [-StartComponentCleanup] [-LimitAccess]
 [-ResetBase] [-Defer] [-Source <String[]>] [-NoRestart] -Path <String> [-WindowsDirectory <String>]
 [-SystemDrive <String>] [-LogPath <String>] [-ScratchDirectory <String>] [-LogLevel <LogLevel>]
 [<CommonParameters>]
```

### Online
```
Repair-WindowsImage [-CheckHealth] [-ScanHealth] [-RestoreHealth] [-StartComponentCleanup] [-LimitAccess]
 [-ResetBase] [-Defer] [-Source <String[]>] [-NoRestart] [-Online] [-WindowsDirectory <String>]
 [-SystemDrive <String>] [-LogPath <String>] [-ScratchDirectory <String>] [-LogLevel <LogLevel>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Repair-WindowsImage** cmdlet repairs a Windows image in a WIM or VHD file.

Use the *Online* parameter to specify the running operating system on your local computer, or use the *Path* parameter to specify the location of a mounted Windows image.

The *LimitAccess* parameter prevents access to Windows Update (WU) as a *Source* for repairing online images.

The *CheckHealth* parameter checks whether the image has been flagged as corrupted by a failed process and whether the corruption can be repaired.

The *ScanHealth* parameter scans the image for component store corruption.
This operation will take several minutes.

The *RestoreHealth* parameter scans the image for component store corruption, and then performs repair operations automatically.
This operation will take several minutes.

The *Source* parameter specifies the location of known good versions of files that can be used for the repair, such as a path to the root directory of a mounted image.

*CheckHealth*, *ScanHealth*, *RestoreHealth*, *Source*, and *LimitAccess* can only be used when servicing images that are running at least Windows 8 or Windows Server 2012.

## EXAMPLES

### Example 1: Scan an image for corruption
```
PS C:\> Repair-WindowsImage -Path "C:\offline\Mount" -ScanHealth
```

This command scans the specified image for component store corruption.

### Example 2: Check an image for corruption and whether to repair the image
```
PS C:\> Repair-WindowsImage -Path "C:\offline\Mount" -CheckHealth
```

This command checks whether the specified image has been flagged as corrupted by a failed process and whether the corruption can be repaired.

### Example 3: Check an image for corruption and repairs the image
```
PS C:\> Repair-WindowsImage -Online -RestoreHealth -Source "C:\Mounted\VHD\Windows\WinSxS", "C:\Windows\TEMP" -LimitAccess
```

This command scans the specified image for component store corruption, and then performs repair operations automatically.

## PARAMETERS

### -CheckHealth
Checks whether the image has been flagged as corrupted by a failed process and whether the corruption can be repaired.

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

### -Defer
Defers cleanup operations until the next automatic maintenance.

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

### -LimitAccess
Prevents DISM from contacting Windows Update (WU) when searching for the source files to repair an online image.

*LimitAccess* can only be used when servicing images that are running at least Windows 8, Windows Server 2012, or Windows  Preinstallation Environment (Windows PE) 4.0.

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

### -NoRestart
Suppresses reboot.
If a reboot is not required, this command does nothing.
This option will keep the application from prompting for a restart or keep it from restarting automatically.

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

### -Online
Specifies that the action is to be taken on the operating system that is currently running on the local computer.

```yaml
Type: SwitchParameter
Parameter Sets: Online
Aliases:

Required: True
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
Parameter Sets: Offline
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResetBase
Resets the base of superseded components to further reduce the component store size.

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

### -RestoreHealth
Scans the image for component store corruption, and then performs repair operations automatically.
This operation will take several minutes.

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

### -ScanHealth
Scans the image for component store corruption.
This operation will take several minutes.

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

### -Source
Specifies the location of the files that are required to repair an image.
You can specify the Windows directory of a mounted image or a running Windows installation that is shared on the network.

If you specify multiple *Source* arguments, the files are gathered from the first location where they are found and the rest of the locations are ignored.
Separate source locations with a comma.

If you do not specify a *Source*, the default location set by Group Policy is used.
Windows Update (WU) is also used for online images.

*Source* can only be used when servicing images that are running at least Windows 8 or Windows Server 2012.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StartComponentCleanup
Cleans up superseded components to reduce the size of the component store.

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

### -SystemDrive
Specifies the path to the location of the BootMgr files.
This is necessary only when the BootMgr files are located on a partition other than the one that you are running the command from.
Use -SystemDrive to service an installed Windows image from a Windows PE environment.

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

### -WindowsDirectory
Specifies the path to the Windows directory relative to the image path.
This cannot be the full path to the Windows directory; it should be a relative path.
If not specified, the default is the Windows directory in the root of the offline image directory.

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

### Microsoft.Dism.Commands.ImageInfoObject

### Microsoft.Dism.Commands.MountedImageInfoObject

## OUTPUTS

### Microsoft.Dism.Commands.ImageObjectWithState

## NOTES

## RELATED LINKS

[Mount-WindowsImage](./Mount-WindowsImage.md)

[Dismount-WindowsImage](./Dismount-WindowsImage.md)

[Get-WindowsImage](./Get-WindowsImage.md)

[Save-WindowsImage](./Save-WindowsImage.md)

