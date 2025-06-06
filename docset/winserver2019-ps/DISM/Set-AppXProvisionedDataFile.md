---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Dism.PowerShell.dll-Help.xml
Module Name: DISM
ms.date: 12/21/2016
online version: https://learn.microsoft.com/powershell/module/dism/set-appxprovisioneddatafile?view=windowsserver2019-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-AppXProvisionedDataFile
---

# Set-AppXProvisionedDataFile

## SYNOPSIS
Adds custom data into the specified app (.appx) package that has been provisioned in a Windows image.

## SYNTAX

### Offline
```
Set-AppXProvisionedDataFile -PackageName <String> -CustomDataPath <String> -Path <String>
 [-WindowsDirectory <String>] [-SystemDrive <String>] [-LogPath <String>] [-ScratchDirectory <String>]
 [-LogLevel <LogLevel>] [<CommonParameters>]
```

### Online
```
Set-AppXProvisionedDataFile -PackageName <String> -CustomDataPath <String> [-Online]
 [-WindowsDirectory <String>] [-SystemDrive <String>] [-LogPath <String>] [-ScratchDirectory <String>]
 [-LogLevel <LogLevel>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-AppXProvisionedDataFile** cmdlet adds custom data into the specified app (.appx) package that has been provisioned in a Windows image.
The specified app (.appx) package must already be added to the image prior to adding custom data.

You cannot install an app package (.appx) on an operating system that does not support apps for at least Windows® 8.
Apps are not supported on Server Core installations of Windows Server, Windows PE, or on any versions of Windows older than Windows 8 and Windows Server 2012.

To install and run apps on Windows Server, you must install the [Desktop Experience](https://go.microsoft.com/fwlink/?LinkId=247330).

Use the *Online* parameter to specify the running operating system on your local computer, or use the *Path* parameter to specify the location of a mounted Windows image.

## EXAMPLES

### Example 1: Add a custom data file to an app package for the running operating system
```
PS C:\> Set-AppXProvisionedDataFile -Online -PackageName "MyAppxPkg" -CustomDataPath "c:\Appx\myCustomData.dat"
```

This command adds the custom data file, c:\Appx\myCustomData.dat, into the app package, MyAppxPkg, that has been added to the running Windows operating system.

### Example 2: Add a custom data file to an app package for a mounted image
```
PS C:\> Set-AppxProvisionedDataFile -Path c:\offline -PackageName MyAppxPkg -CustomDataPath c:\Appx\myCustomData.dat
```

This command adds the custom data file, c:\Appx\myCustomData.dat, into the app package, MyAppxPkg, that has been added to the Windows image mounted to c:\offline.

## PARAMETERS

### -CustomDataPath
Specifies an optional custom data file for an app.
You can specify any file name.
The file will be renamed to Custom.dat when it is added to the image.
If a Custom.dat file already exists, it will be overwritten.

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

### Microsoft.Dism.Commands.AppxPackageObject

## OUTPUTS

### Microsoft.Dism.Commands.ImageObject

## NOTES

## RELATED LINKS

[Add-AppxProvisionedPackage](./Add-AppxProvisionedPackage.md)

[Get-AppxProvisionedPackage](./Get-AppxProvisionedPackage.md)

[Remove-AppxProvisionedPackage](./Remove-AppxProvisionedPackage.md)

