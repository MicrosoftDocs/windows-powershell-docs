---
external help file: Microsoft.Dism.PowerShell.dll-Help.xml
ms.assetid: 65D8D1DB-A8F2-470F-9095-B746146B630C
ms.reviewer:
ms.author: kenwith
author: kenwith
online version: 
schema: 2.0.0
---

# Clear-WindowsCorruptMountPoint

## SYNOPSIS
Deletes all of the resources associated with a mounted image that has been corrupted.

## SYNTAX

```
Clear-WindowsCorruptMountPoint [-LogPath <String>] [-ScratchDirectory <String>] [-LogLevel <LogLevel>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Clear-WindowsCorruptMountPoint** cmdlet deletes all of the resources associated with a mounted image that has been corrupted.

## EXAMPLES

### Example 1: Delete all resources associated with a mounted image
```
PS C:\>Clear-WindowsCorruptMountPoint
```

This command deletes all of the resources on the computer that are associated with a mounted image that has been corrupted.

## PARAMETERS

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
Aliases: 
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Dism.Commands.BasicDismObject

## OUTPUTS

### Microsoft.Dism.Commands.BaseDismObject

## NOTES

## RELATED LINKS

