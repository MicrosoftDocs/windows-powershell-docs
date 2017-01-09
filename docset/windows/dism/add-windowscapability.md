---
author: brianlic
description: 
external help file: Microsoft.Dism.PowerShell.dll-Help.xml
keywords: powershell, cmdlet
manager: alanth
ms.date: 2016-12-21
ms.prod: powershell
ms.technology: powershell
ms.topic: reference
online version: 
schema: 2.0.0
title: Add-WindowsCapability
ms.assetid: 64CA40D3-F695-4E1D-8F4B-9543FD5C1A8A
---

# Add-WindowsCapability

## SYNOPSIS
Installs a Windows capability package on the specified operating system image.

## SYNTAX

### Online
```
Add-WindowsCapability -Name <String> [-LimitAccess] [-Source <String[]>] [-Online] [-WindowsDirectory <String>]
 [-SystemDrive <String>] [-LogPath <String>] [-ScratchDirectory <String>] [-LogLevel <LogLevel>]
 [<CommonParameters>]
```

### Offline
```
Add-WindowsCapability -Name <String> [-LimitAccess] [-Source <String[]>] -Path <String>
 [-WindowsDirectory <String>] [-SystemDrive <String>] [-LogPath <String>] [-ScratchDirectory <String>]
 [-LogLevel <LogLevel>] [<CommonParameters>]
```

## DESCRIPTION
The **Add-WindowsCapability** cmdlet acquires a Windows capability package from a priority-ordered list of source locations, and then installs the package on the specified operating system image.

## EXAMPLES

### Example 1: Add a Windows capability package to an image
```
PS C:\>Add-WindowsCapability -Name "Language.TextToSpeech~~~fr-FR~0.0.1.0" -Path "C:\offline" -Source "C:\Windows\winsxs"
```

This command adds a Windows capability package to the operating system image specified by the **Name** parameter at the path C:\offline.
The **Source** parameter specifies the location of required files.

### Example 2: Add a Windows capability package to the local host
```
PS C:\>Add-WindowsCapability -Name "Language.TextToSpeech~~~fr-FR~0.0.1.0" -Online -LimitAccess -Source "C:\Windows\winsxs"
```

This command adds a windows capabilities package the local host while the operating system continues to run.

## PARAMETERS

### -LimitAccess
Indicates that this cmdlet does not access Windows Update for the source package.

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
1 = Errors only
2 = Errors and warnings
3 = Errors, warnings, and information
4 = All of the information listed previously, plus debug output

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
Specifies the identity of the capability to add to an operating system image.

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

### -Online
Indicates that the cmdlet operates on a running operating system on the local host.

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
If the directory named Windows is not a subdirectory of the root directory, -WindowsDirectory must be specified.

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
Specifies the location of the files that are required to add a Windows capability package to an image.
You can specify the Windows directory of a mounted image or a running Windows installation that is shared on the network.

If you specify multiple **Source** arguments, the files are gathered from the first location where they are found and the rest of the locations are ignored.
Separate source locations with a comma.

If you do not specify a **Source**, the default location set by Group Policy is used.
Windows Update is also used for online images.

**Source** can only be used when servicing images that are running at least Windows® 8 or Windows Server® 2012.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Dism.Commands.ImageObject

## NOTES

## RELATED LINKS

[Get-WindowsCapability](./Get-WindowsCapability.md)

[Remove-WindowsCapability](./Remove-WindowsCapability.md)

