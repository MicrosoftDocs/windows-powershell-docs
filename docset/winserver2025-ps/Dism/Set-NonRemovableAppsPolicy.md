---
description: Sets an app package as non-removable (can not be uninstalled).
external help file: Microsoft.Dism.PowerShell.dll-Help.xml
Module Name: Dism
ms.date: 10/07/2021
online version: https://learn.microsoft.com/powershell/module/dism/set-nonremovableappspolicy?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-NonRemovableAppsPolicy
---

# Set-NonRemovableAppsPolicy

## SYNOPSIS
Sets an app package as non-removable (can not be uninstalled).

## SYNTAX

### Offline
```
Set-NonRemovableAppsPolicy -PackageFamilyName <String> -NonRemovable <Int32> -Path <String>
 [-WindowsDirectory <String>] [-SystemDrive <String>] [-LogPath <String>] [-ScratchDirectory <String>]
 [-LogLevel <LogLevel>] [<CommonParameters>]
```

### Online
```
Set-NonRemovableAppsPolicy -PackageFamilyName <String> -NonRemovable <Int32> [-Online]
 [-WindowsDirectory <String>] [-SystemDrive <String>] [-LogPath <String>] [-ScratchDirectory <String>]
 [-LogLevel <LogLevel>] [<CommonParameters>]
```

## DESCRIPTION
The Set-NonRemovableAppsPolicy cmdlet sets an installed app package as either removable (capable of
being uninstalled) or non-removable (can not be uninstalled).

## EXAMPLES

### Example 1: Set the app package Application1 as non-removable
```powershell
PS> Set-NonRemovableAppsPolicy -Online -PackageFamilyName Application1_1.0.0.0+x64__ms7gsqeatfeb6 -NonRemovable 1
```

This command sets the app package *Application1* as non-removable.

### Example 2: Set the app package Application1 as removable
```powershell
PS> Set-NonRemovableAppsPolicy -Online -PackageFamilyName Application1_1.0.0.0+x64__ms7gsqeatfeb6 -NonRemovable 0
```
This command sets the app package *Application1* as removable.

### Example 3: Sets the app package Application1 as non-removable on an offline Windows image
```powershell
PS> Set-NonRemovableAppsPolicy -Path ".\wim\image.wim" -PackageFamilyName Application1_1.0.0.0+x64__ms7gsqeatfeb6 -NonRemovable 1
```

This command sets the app package *Application1* as non-removable for offline Windows image named
*image.win*.

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
Accepted values: Errors, Warnings, WarningsInfo, Debug

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LogPath
Specifies the full path and file name to log to. If not set, the default is
`%WINDIR%\Logs\Dism\dism.log`. In Windows PE, the default directory is the RAMDISK scratch space
which can be as low as 32 MB. The log file will automatically be archived. The archived log file
will be saved with .bak appended to the file name and a new log file will be generated. Each time
the log file is archived the .bak file will be overwritten. When using a network share that is not
joined to a domain, use the net use command together with domain credentials to set access
permissions before you set the log path for the DISM log.

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

### -NonRemovable
Configures an app package as removable or non-removable.

 Accepted values are as follows:
- 0 = Sets the application as removable and can be uninstalled.
- 1 = Sets the application as non-removable and unable to be uninstalled.


```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Online
Specifies that the action is to be taken on the operating system that is currently running on the
local computer.

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

### -PackageFamilyName
Specifies the Package Family Name of the app package to set as non-removable.

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
Specifies the full path to the root directory of the offline Windows image that you will service. If
the directory named Windows is not a subdirectory of the root directory, *WindowsDirectory* must be
specified.

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
The directory must exist locally. If not specified, the `\Windows\%Temp%` directory will be used,
with a subdirectory name of a randomly generated hexadecimal value for each run of DISM. Items in
the scratch directory are deleted after each operation. You should not use a network share location
as a scratch directory to expand a package (.cab or .msu file) for installation. The directory used
for extracting files for temporary usage during servicing should be a local directory.

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
Specifies the path to the location of the BootMgr files. This is necessary only when the BootMgr
files are located on a partition other than the one that you are running the command from. Use
-SystemDrive to service an installed Windows image from a Windows PE environment.

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
Specifies the path to the Windows directory relative to the image path. This cannot be the full path
to the Windows directory; it should be a relative path. If not specified, the default is the Windows
directory in the root of the offline image directory.

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

### System.String

### System.Management.Automation.SwitchParameter

### Microsoft.Dism.Commands.LogLevel

## OUTPUTS

### Microsoft.Dism.Commands.ImageObject

## NOTES

## RELATED LINKS

[https://go.microsoft.com/fwlink/?LinkId=293633](https://go.microsoft.com/fwlink/?LinkId=293633)

