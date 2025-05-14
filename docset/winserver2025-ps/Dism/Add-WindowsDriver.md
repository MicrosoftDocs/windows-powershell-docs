---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Dism.PowerShell.dll-Help.xml
Module Name: System.Object[]
ms.date: 12/21/2016
online version: https://learn.microsoft.com/powershell/module/dism/add-windowsdriver?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-WindowsDriver
---

# Add-WindowsDriver

## SYNOPSIS
Adds a driver to an offline Windows image.

## SYNTAX

```
Add-WindowsDriver [-Recurse] [-ForceUnsigned] [-Driver <String>] [-BasicDriverObject <BasicDriverObject>]
 [-AdvancedDriverObject <AdvancedDriverObject>] -Path <String> [-WindowsDirectory <String>]
 [-SystemDrive <String>] [-LogPath <String>] [-ScratchDirectory <String>] [-LogLevel <LogLevel>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Add-WindowsDriver** cmdlet adds third-party driver packages to an offline Windows image.

Use the *Path* parameter to specify the location of a mounted Windows image.

Use the *Driver* parameter to specify the location of an .inf driver file or a folder containing one or more .inf driver files.

Use the *ForceUnsigned* parameter to add unsigned .inf files to an x64-based image.

## EXAMPLES

### Example 1: Add drivers to an image
```
PS C:\> Add-WindowsDriver -Path "c:\offline" -Driver "c:\test\drivers" -Recurse
```

This command adds any drivers in the c:\test\drivers folder or any of its subdirectories to the Windows operating system image that is mounted to c:\offline.

### Example 2: Add an unsigned driver package
```
PS C:\> Add-WindowsDriver -Path "c:\offline" -Driver "c:\test\drivers\Usb\Usb.inf" -ForceUnsigned
```

This command adds the unsigned driver package, Usb.inf, to the Windows image that is mounted to c:\offline.

## PARAMETERS

### -AdvancedDriverObject
Specifies an object containing detailed information about the driver you want to add.
This can be piped from the output of Export-WindowsDriver or Get-WindowsDriver.

```yaml
Type: AdvancedDriverObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -BasicDriverObject
Provides an object containing basic information about the driver you want to add.
This can be piped from the output of **Export-WindowsDriver** or **Get-WindowsDriver**.

```yaml
Type: BasicDriverObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Driver
Specifies the .inf file or folder containing the .inf files of the drivers you want to add.
When you specify a folder, .inf files that are not valid driver packages are ignored.
These files are reported on the console when the command runs, and a warning is included in the log file.
You will not receive an error message.

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

### -ForceUnsigned
Adds unsigned drivers to an x64 image.
The *ForceUnsigned* parameter overrides the requirement that drivers that are installed on X64-based computers must have a digital signature.
For more information about driver signing requirements, see [Windows Deployment Options](https://go.microsoft.com/fwlink/?LinkId=214574) in the TechNet Library.

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

### -Recurse
Includes all subfolders when searching for drivers to add.

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

### Microsoft.Dism.Commands.BasicDriverObject

### Microsoft.Dism.Commands.AdvancedDriverObject

## OUTPUTS

### Microsoft.Dism.Commands.BasicDriverObject

### Microsoft.Dism.Commands.ImageObject

## NOTES

## RELATED LINKS

[Get-WindowsDriver](./Get-WindowsDriver.md)

[Remove-WindowsDriver](./Remove-WindowsDriver.md)

