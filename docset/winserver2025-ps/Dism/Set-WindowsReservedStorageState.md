---
external help file: Microsoft.Dism.PowerShell.dll-Help.xml
Module Name: System.Object[]
online version: https://learn.microsoft.com/powershell/module/dism/set-windowsreservedstoragestate?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-WindowsReservedStorageState

## SYNOPSIS
Sets the reserved storage state of the image.

## SYNTAX

```
Set-WindowsReservedStorageState -State <ReservedStorageState> [-LogPath <String>] [-ScratchDirectory <String>]
 [-LogLevel <LogLevel>] [<CommonParameters>]
```

## DESCRIPTION
Sets the state of reserved storage. This command line option is only supported for online Windows images. If reserved storage is in use, it may not be disabled, and the following error is returned: <i>This operation is not supported when reserved storage is in use. Please wait for any servicing operations to complete and then try again later. </i>Changes to reserved storage state are reflected in Sysprep generalized Windows images. For more information see [Sysprep (Generalize) a Windows installation](/windows-hardware/manufacture/desktop/sysprep--system-preparation--overview).

## EXAMPLES

### Example 1
```powershell
PS C:\> Set-WindowsReservedStorageState -State Enabled -Online
```

This command enables Windows reserved storage on the local host.

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

### -State
The reserved storage state of the image, either Disabled or Enabled.

```yaml
Type: ReservedStorageState
Parameter Sets: (All)
Aliases:
Accepted values: Disabled, Enabled

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Dism.Commands.ReservedStorageState

### System.String

### Microsoft.Dism.Commands.LogLevel

## OUTPUTS

### Microsoft.Dism.Commands.ReservedStorageStateObject

## NOTES
Supported on Windows 10, version 2004

## RELATED LINKS
[Get-WindowsReservedStorageState](./Get-WindowsReservedStorageState.md)
