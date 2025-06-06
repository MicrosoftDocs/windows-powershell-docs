---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Dism.PowerShell.dll-Help.xml
Module Name: DISM
ms.date: 12/21/2016
online version: https://learn.microsoft.com/powershell/module/dism/get-windowspackage?view=windowsserver2016-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WindowsPackage
---

# Get-WindowsPackage

## SYNOPSIS
Gets information about packages in a Windows image.

## SYNTAX

### Offline
```
Get-WindowsPackage [-PackagePath <String>] [-PackageName <String>] -Path <String> [-WindowsDirectory <String>]
 [-SystemDrive <String>] [-LogPath <String>] [-ScratchDirectory <String>] [-LogLevel <LogLevel>]
 [<CommonParameters>]
```

### Online
```
Get-WindowsPackage [-PackagePath <String>] [-PackageName <String>] [-Online] [-WindowsDirectory <String>]
 [-SystemDrive <String>] [-LogPath <String>] [-ScratchDirectory <String>] [-LogLevel <LogLevel>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-WindowsPackage** cmdlet gets information about all packages in a Windows image or about a specific package that is provided as a .cab file.

Use the *Online* parameter to specify the running operating system on your local computer, or use the *Path* parameter to specify the location of a mounted Windows image.

Use either the *PackageName* or *PackagePath* parameter to get more detailed information about a specific package in the Windows image such as whether the package can be installed completely offline without booting the image.

You cannot use this command to obtain detailed package information for .msu files, only .cab files.

## EXAMPLES

### Example 1: Lists packages in a mounted image
```
PS C:\> Get-WindowsPackage -Path "c:\offline"
```

This command lists all of the packages in the Windows image that is mounted to c:\offline.

### Example 2: Lists details about a package in a mounted image
```
PS C:\> Get-WindowsPackage -Path "c:\offline" -PackageName "Microsoft-Windows-Backup-Package~31bf3856ad364e35~x86~~6.1.7601.16525"
```

This command displays detailed information about the specified package in the Windows image that is mounted to c:\offline.

## PARAMETERS

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
Specifies the name of a package as it is listed in the Windows image.
Use the *PackageName* parameter to get more detailed information about a specific package in the Windows image, such as whether the package can be installed completely offline without booting the image.

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

### -PackagePath
Specifies the location of a .cab file in the Windows image.
Use the *PackagePath* parameter to get more detailed information about a specific package in the Windows image, such as whether the package can be installed completely offline without booting the image.

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

## OUTPUTS

### Microsoft.Dism.Commands.BasicPackageObject

### Microsoft.Dism.Commands.AdvancedPackageObject

## NOTES

## RELATED LINKS

[Add-WindowsPackage](./Add-WindowsPackage.md)

[Remove-WindowsPackage](./Remove-WindowsPackage.md)

