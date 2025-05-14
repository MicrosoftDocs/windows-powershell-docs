---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Dism.PowerShell.dll-Help.xml
Module Name: System.Object[]
ms.date: 12/21/2016
online version: https://learn.microsoft.com/powershell/module/dism/new-windowscustomimage?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-WindowsCustomImage
---

# New-WindowsCustomImage

## SYNOPSIS
Captures an image of customized or serviced Windows components on a Windows Image File Boot (WIMBoot) configured device.

## SYNTAX

```
New-WindowsCustomImage -CapturePath <String> [-ConfigFilePath <String>] [-CheckIntegrity] [-Verify]
 [-LogPath <String>] [-ScratchDirectory <String>] [-LogLevel <LogLevel>] [<CommonParameters>]
```

## DESCRIPTION
The **New-WindowsCustomImage** cmdlet captures image customizations into a new WIM file on a Windows Image File Boot (WIMBoot) system.

Captured directories include all subfolders and data.

You cannot capture an empty directory.

Note: This command only captures customization files.

The command cannot be used to capture installation files into a new WIM.

## EXAMPLES

### Example 1: Capture image customization files
```
PS C:\> New-WindowsCustomImage -CapturePath "c:\"
```

This command captures image customization files in a WIM and saves the files on the c:\ directory.

## PARAMETERS

### -CapturePath
Specifies the drive or path to the Windows operating system that is to be captured to an image file.

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

### -CheckIntegrity
Detects and tracks .wim file corruption when used with the **Add-WindowsImage**, **Dismount-WindowsImage**, or **Save-WindowsImage** cmdlet.
CheckIntegrity stops the operation if DISM detects that the .wim file is corrupted when used with the **Expand-WindowsImage** or **Mount-WindowsImage** cmdlet.

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

### -ConfigFilePath
Specifies the location of a configuration file that lists exclusions for image capture and compress commands.
For more information, see [DISM Configuration List and WimScript.ini Files](https://go.microsoft.com/fwlink/?LinkID=313768).

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

### -Verify
Checks for errors and file duplication.
 During an apply operation, for example, using the **Add-WindowsImage** cmdlet, the size and the hash of the file being applied are checked against the image file to verify they are both equal.
 During a capture operation, for example, when using the **New-WindowsImage** cmdlet, after the files is captured into a Windows image, the file is written to a temporary file and compared on a bit-by-bit basis with the original file.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### none

## OUTPUTS

### Microsoft.Dism.Commands.ImageObject

## NOTES

## RELATED LINKS

