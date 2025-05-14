---
audience: ITPro
ms.localizationpriority: Low
description: Use this topic to help prevent the uninstall of specific Windows apps with Windows PowerShell.
external help file: Microsoft.Windows.Appx.PackageManager.Commands.dll-help.xml
Module Name: Appx
ms.date: 02/05/2020
online version: https://learn.microsoft.com/powershell/module/appx/set-nonremovableappspolicy?view=windowsserver2019-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-NonRemovableAppsPolicy
---

# Set-NonRemovableAppsPolicy

## SYNOPSIS
Sets an app packages as non-removable (can not be uninstalled).

## SYNTAX

### ByOffline
```powershell
Set-NonRemovableAppsPolicy 
    -PackageFamilyName <string> 
    -NonRemovable <int> 
    -Path <string> 
    [-WindowsDirectory <string>]
    [-SystemDrive <string>] 
    [-LogPath <string>] 
    [-ScratchDirectory <string>] 
    [-LogLevel {Errors | Warnings | WarningsInfo}]
    [<CommonParameters>]
```

### ByOnline
```powershell
Set-NonRemovableAppsPolicy 
    -PackageFamilyName <string> 
    -NonRemovable <int> 
    -Online 
    [-WindowsDirectory <string>] 
    [-SystemDrive <string>] 
    [-LogPath <string>] 
    [-ScratchDirectory <string>] 
    [-LogLevel {Errors | Warnings | WarningsInfo}] 
    [<CommonParameters>]
```

## DESCRIPTION
The **Set-NonRemovableAppsPolicy** cmdlet sets an installed app package as either removable (capable of being uninstalled) or non-removable (can not be uninstalled). An app package has a .msix or .appx file name extension.

## EXAMPLES

### Example 1: Set the app package Application1 as non-removable
```
PS C:\> Set-NonRemovableAppsPolicy -Online -PackageFamilyName Application1_1.0.0.0+x64__ms7gsqeatfeb6 -NonRemovable 1
```

This command sets the app package Application1 as non-removable.

### Example 2: Set the app package Application1 as removable
```
PS C:\> Set-NonRemovableAppsPolicy -Online -PackageFamilyName Application1_1.0.0.0+x64__ms7gsqeatfeb6 -NonRemovable 0
```
This command sets the app package Application1 as removable.

### Example 3: Sets the app package Application1 as non-removable on an offline Windows image
```
PS C:\> Set-NonRemovableAppsPolicy -Path ".\wim\image.wim" -PackageFamilyName Application1_1.0.0.0+x64__ms7gsqeatfeb6 -NonRemovable 1
```

This command sets the app package Application1 as non-removable on an offline Windows image.

## PARAMETERS

### -PackageFamilyName
Specifies the Package Family Name of the app package that will have it's non-removable status set.

```yaml
Type: String
Parameter Sets: ByOnline, ByOffline
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NonRemovable
Specifies that the app package will be configured as non-removable or not. Accepted values are as follows:
- 1 = Sets the application as non-removable, and unable to be uninstalled.
- 0 = Sets the application as removable, and capable of being uninstalled.

```yaml
Type: Integer
Parameter Sets: ByOnline, ByOffline
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
Parameter Sets: ByOnline
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Path
Specifies the full path to the root directory of the offline Windows image that you will service. If the directory named Windows is not a subdirectory of the root directory, WindowsDirectory must be specified.

```yaml
Type: String
Parameter Sets: ByOffline
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ScratchDirectory
Specifies a temporary directory that will be used when extracting files for use during servicing. The directory must exist locally. If not specified, the `\Windows\Temp` directory will be used, with a subdirectory name of a randomly generated hexadecimal value for each run of DISM. Items in the scratch directory are deleted after each operation. You should not use a network share location as a scratch directory to expand a package(.cab or .msu file) for installation.

```yaml
Type: String
Parameter Sets: ByOnline, ByOffline
Aliases: 

Required: False
Position: Named
Default value: \Windows\Temp
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SystemDrive
Specifies the path to the location of the BootMgr files. This is necessary only when the BootMgr files are located on a partition other than the one that you are running the command from. Use -SystemDrive to inquire an installed Windows image from a Windows PE environment.

```yaml
Type: String
Parameter Sets: ByOnline, ByOffline
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -WindowsDirectory
Specifies the path to the Windows directory relative to the image path. This cannot be the full path to the Windows directory; it should be a relative path. If not specified, the default is the Windows directory in the root of the offline image directory.

```yaml
Type: String
Parameter Sets: ByOffline
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LogPath
Specifies the full path and file name to log to. If not set, the default is `%WINDIR%\Logs\Dism\dism.log`. In Windows PE, the default directory is the RAMDISK scratch space which can be as small as 32MB. The log file will automatically be archived. The archived log file will be saved with .bak appended to the file name and a new log file will be generated. Each time the log file is archived the .bak file will be overwritten. When using a network share that is not joined to a domain, use the net use command together with domain credentials to set access permissions before you set the log path for the DISM log.

```yaml
Type: String
Parameter Sets: ByOnline, ByOffline
Aliases: LP

Required: False
Position: Named
Default value: %WINDIR%\Logs\Dism\dism.log
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LogLevel
Specifies the maximum output level shown in the logs. The default log level is 3. The accepted values are as follows:
- 1 = Error
- 2 = Errors and warnings
- 3 = Errors, warnings, and information
- 4 = All of the information listed previously, plus debug output

```yaml
Type: Loglevel
Parameter Sets: ByOnline, ByOffline
Aliases: LL

Required: False
Position: Named
Default value: 3
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String[]

### System.IO.FileInfo

## OUTPUTS

## NOTES

## RELATED LINKS
