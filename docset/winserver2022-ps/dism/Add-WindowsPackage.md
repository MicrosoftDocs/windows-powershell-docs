---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Dism.PowerShell.dll-Help.xml
Module Name: System.Object[]
ms.date: 12/21/2016
online version: https://learn.microsoft.com/powershell/module/dism/add-windowspackage?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-WindowsPackage
---

# Add-WindowsPackage

## SYNOPSIS
Adds a single .cab or .msu file to a Windows image.

## SYNTAX

### Online
```
Add-WindowsPackage -PackagePath <String> [-IgnoreCheck] [-PreventPending] [-NoRestart] [-Online]
 [-WindowsDirectory <String>] [-SystemDrive <String>] [-LogPath <String>] [-ScratchDirectory <String>]
 [-LogLevel <LogLevel>] [<CommonParameters>]
```

### Offline
```
Add-WindowsPackage -PackagePath <String> [-IgnoreCheck] [-PreventPending] [-NoRestart] -Path <String>
 [-WindowsDirectory <String>] [-SystemDrive <String>] [-LogPath <String>] [-ScratchDirectory <String>]
 [-LogLevel <LogLevel>] [<CommonParameters>]
```

## DESCRIPTION
The **Add-WindowsPackage** cmdlet installs a specified .cab or .msu package in the image.

## EXAMPLES

### Example 1: Add a package to an online image
```
PS C:\> Add-WindowsPackage -Online -PackagePath "c:\packages\package.cab"
```

This command adds a .cab package to an online image.

### Example 2: Add a file to a mounted image
```
PS C:\> Add-WindowsPackage -Path "c:\offline" -PackagePath "c:\packages\demo_package.msu" -PreventPending
```

This command adds an .msu file to a mounted Windows image unless there are pending actions on the package or the image.

### Example 3: Add several packages to a mounted image
```
PS C:\> Add-WindowsPackage -Path "c:\offline" -PackagePath "c:\packages" -IgnoreCheck
```

This command adds all of the packages in a folder to a mounted Windows image without checking if they are applicable to the image.

## PARAMETERS

### -IgnoreCheck
Skips the applicability check for each package.

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

### -PackagePath
Specifies the location of the package to add to the image.

Valid values are:

- A single .cab or .msu file.
- A folder that contains a single expanded .cab file.
- A folder that contains a single .msu file.
- A folder that contains multiple .cab or .msu files.

If *PackagePath* is a folder that contains a .cab or .msu files at its root, any subfolders will also be recursively checked for .cab and .msu files.

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

### -PreventPending
Skips the installation of the package if the package or Windows image has pending online actions.

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

### Microsoft.Dism.Commands.BasicPackageObject

### Microsoft.Dism.Commands.AdvancedPackageObject

## OUTPUTS

### Microsoft.Dism.Commands.ImageObject

## NOTES

**Checkpoint cumulative updates**

Starting with Windows 11, version 24H2, the latest cumulative update may have a prerequisite cumulative update that is required to be installed first. To install these checkpoint cumulative updates, call Add-WindowsPackage with the target cumulative update. The folder from -PackagePath will be used to discover and install one or more checkpoints as needed. Only the target cumulative update and any prerequisite checkpoint cumulative updates should be in the -PackagePath folder. Cumulative update packages with a revision less than or equal to the target cumulative update will be processed.

## RELATED LINKS

[Get-WindowsPackage](./Get-WindowsPackage.md)

[Remove-WindowsPackage](./Remove-WindowsPackage.md)

