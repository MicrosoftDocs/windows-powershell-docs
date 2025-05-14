---
description: Optimizes the total file size of provisioned packages on the image by replacing identical files with hard links.
external help file: Microsoft.Dism.PowerShell.dll-Help.xml
Module Name: Dism
ms.date: 10/13/2021
online version: https://learn.microsoft.com/powershell/module/dism/optimize-appxprovisionedpackages?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Optimize-AppXProvisionedPackages
---

# Optimize-AppXProvisionedPackages

## SYNOPSIS
Optimizes the total file size of provisioned packages on the image by replacing identical files with
hard links.

## SYNTAX

### Offline
```
Optimize-AppXProvisionedPackages -Path <String> [-WindowsDirectory <String>] [-SystemDrive <String>]
 [-LogPath <String>] [-ScratchDirectory <String>] [-LogLevel <LogLevel>] [<CommonParameters>]
```

## DESCRIPTION
Optimizes the total file size of provisioned packages on the image by replacing identical files with
hard links.

When building an image, mount the disk image, add AppX packages, optimize provisioned packages, then
dismount the disk image.

Once an image with provisioned AppX packages is online,
**Optimize-AppXProvisionedPackages** won't be able to optimize provisioned AppX packages. If you
take an image offline and add packages, only the packages that are provisioned after the image was
brought offline are optimized.

## EXAMPLES

### Example 1: Optimize provisioned packages in an offline Windows image
```powershell
PS> Optimize-AppXProvisionedPackages -Path ".\wim\image.wim"
```

This command optimizes the total file size of provisioned packages in the image named
*image.wim*.

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

### -Online
Do not use. **Optimize-AppXProvisionedPackages** can't optimize provisioned AppX packages if the
image is online.

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

