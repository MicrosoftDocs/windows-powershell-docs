---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Dism.PowerShell.dll-Help.xml
Module Name: System.Object[]
ms.date: 12/21/2016
online version: https://learn.microsoft.com/powershell/module/dism/enable-windowsoptionalfeature?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-WindowsOptionalFeature
---

# Enable-WindowsOptionalFeature

## SYNOPSIS
Enables a feature in a Windows image.

## SYNTAX

### Online
```
Enable-WindowsOptionalFeature -FeatureName <String[]> [-PackageName <String>] [-All] [-LimitAccess]
 [-Source <String[]>] [-NoRestart] [-Online] [-WindowsDirectory <String>] [-SystemDrive <String>]
 [-LogPath <String>] [-ScratchDirectory <String>] [-LogLevel <LogLevel>] [<CommonParameters>]
```

### Offline
```
Enable-WindowsOptionalFeature -FeatureName <String[]> [-PackageName <String>] [-All] [-LimitAccess]
 [-Source <String[]>] [-NoRestart] -Path <String> [-WindowsDirectory <String>] [-SystemDrive <String>]
 [-LogPath <String>] [-ScratchDirectory <String>] [-LogLevel <LogLevel>] [<CommonParameters>]
```

## DESCRIPTION
The **Enable-WindowsOptionalFeature** cmdlet enables or restores an optional feature in a Windows image.

Use the *Online* parameter to specify the running operating system on your local computer, or use the *Path* parameter to specify the location of a mounted Windows image.

The *PackageName* parameter specifies the package that the feature is a component of.
This parameter is optional when the package is the Windows Foundation package.

The *FeatureName* parameter specifies the feature to add.
You can specify more than one feature in the same package.
Separate feature names with a comma.

The *Source* parameter specifies the location of files that are needed to restore a removed feature.

The *LimitAccess* parameter prevents access to Windows Update as a *Source* for restoring features to online images.
The *All* parameter enables all parent features of the specified feature before enabling the specified feature.
The parent feature will be enabled with default values.

## EXAMPLES

### Example 1: Enable an optional feature in the running operating system
```
PS C:\> Enable-WindowsOptionalFeature -Online -FeatureName "Hearts" -All
```

This command enables the optional feature, Hearts, the parent feature for Hearts, and the dependencies for the parent feature in the running Windows operating system.

### Example 2: Enable an optional feature in a mounted operating system image
```
PS C:\> Enable-WindowsOptionalFeature -Path "c:\offline" -FeatureName "Calc" -PackageName "Microsoft.Windows.Calc.Demo~6595b6144ccf1df~x86~en~1.0.0.0"
```

This command enables the optional feature, Calc, in the specified package in the Windows image that is mounted to c:\offline.

### Example 3: Restore an optional feature
```
PS C:\> Enable-WindowsOptionalFeature -Online -FeatureName "MyFeature" -Source "c:\test\mount" -LimitAccess
```

This command restores the optional feature, MyFeature, to the Windows image that is mounted to c:\offline using source files from another Windows image that is mounted to c:\test\mount.
If the files are not found in the source image, this command specifies not to check Windows Update for the source files.

## PARAMETERS

### -All
Enables all parent features of the specified feature.
If a parent feature is required for the specified feature to be enabled in the image, *All* will enable the parent and all of its default dependencies.

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

### -FeatureName
Specifies the name of the feature to be enabled.
Feature names are case sensitive if you are servicing a Windows image running a version of Windows earlier than Windows® 8.
You can use Get-WindowsOptionalFeature to find the name of the feature in the image.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LimitAccess
Prevents DISM from contacting Windows Update when searching for the source files to restore a feature on an online image.

LimitAccess can only be used when servicing images with Windows 8, Windows Server® 2012, Windows® Preinstallation Environment (Windows PE) 4.0 or a later version.

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

### -PackageName
Specifies the name of a package in the Windows image.

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
Specifies the location of the files that are required to restore a feature that has been removed from the image.
You can specify the Windows directory of a mounted image or a running Windows installation that is shared on the network.

If you specify multiple *Source* arguments, the files are gathered from the first location where they are found and the rest of the locations are ignored.
Separate feature names with a comma.

If you do not specify a *Source* for a feature that has been removed, the default location set by Group Policy is used.
Windows Update is also used for online images.

*Source* can only be used when servicing an image with Windows 8 or Windows Server 2012 or a later version.

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

### Microsoft.Dism.Commands.BasicFeatureObject

### Microsoft.Dism.Commands.AdvancedFeatureObject

## OUTPUTS

### Microsoft.Dism.Commands.ImageObject

## NOTES

## RELATED LINKS

[Disable-WindowsOptionalFeature](./Disable-WindowsOptionalFeature.md)

[Get-WindowsOptionalFeature](./Get-WindowsOptionalFeature.md)

[Add-WindowsPackage](./Add-WindowsPackage.md)

