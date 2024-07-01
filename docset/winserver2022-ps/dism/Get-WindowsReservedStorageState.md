---
external help file: Microsoft.Dism.PowerShell.dll-Help.xml
Module Name: System.Object[]
online version: https://learn.microsoft.com/powershell/module/dism/get-windowsreservedstoragestate?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-WindowsReservedStorageState

## SYNOPSIS
Gets the reserved storage state of the image.

## SYNTAX

```
Get-WindowsReservedStorageState [-LogPath <String>] [-ScratchDirectory <String>] [-LogLevel <LogLevel>]
 [<CommonParameters>]
```

## DESCRIPTION
Gets the current state of reserved storage. This command is only supported with the online Windows image.

## EXAMPLES

### Example 1
```powershell
PS C:\> Get-WindowsReservedStorageState
```

This command gets the Windows reserved storage state on the local host.

## PARAMETERS

### -LogLevel
Specifies the output level shown in the logs.
The accepted values are as follows:
- Errors (or '0') - shows error events. Could be combined with Warnings or WarningsInfo
- Warnings (or '1') - shows warning events
- WarningsInfo (or '2') - shows information log records

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### Microsoft.Dism.Commands.LogLevel

## OUTPUTS

### Microsoft.Dism.Commands.ReservedStorageStateObject

## NOTES
Supported on Windows 10, version 2004

## RELATED LINKS
[Set-WindowsReservedStorageState](./Set-WindowsReservedStorageState.md)
