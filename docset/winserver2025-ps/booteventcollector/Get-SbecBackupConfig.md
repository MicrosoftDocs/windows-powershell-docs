---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: BootEventCollector-help.xml
Module Name: BootEventCollector
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/booteventcollector/get-sbecbackupconfig?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-SbecBackupConfig
---

# Get-SbecBackupConfig

## SYNOPSIS
Get the backup configuration files that are available to restore.

## SYNTAX

```
Get-SbecBackupConfig [[-ComputerName] <String[]>] [[-CimSession] <CimSession[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SbecBackupConfig** cmdlet gets the backup configuration files that are available to restore.

Whenever a new configuration is set in the Boot Event Collector, the old configuration is saved to a backup file (see Checkpoint-SbecActiveConfig for more information).
Normally, the backup files contain the UTC timestamp in the format YYYYMMDDhhmmssfffffff ("f" being the digits of the fractions of a second) in their names, allowing you to track the history of changes and to restore the older configurations.
If the collector was started with the *noCfgHistory* switch, only one last configuration is kept in a file with the fixed name, and the last modification timestamp on it is used to track the configuration timestamp.
The way to specify the switch for the service is by creating the registry value "HKLM:\SYSTEM\CurrentControlSet\Services\BootEventCollector\Parameters\noCfgHistory" with type REG_DWORD set to 1.

**Get-SbecBackupConfig** returns the list of the available backup configuration files, in the order from the most recent to the oldest.
You can restore these files explicitly with Restore-SbecBackupConfig, or navigate them sequentially with Undo-SbecActiveConfig and Redo-SbecActiveConfig.

Even though it's possible to create the backup files with future timestamps (either manually or when the computer's notion of time is moved back abruptly), and these files are listed by **Get-SbecBackupConfig**, they are ignored by the **Undo-SbecActiveConfig** and **Redo-SbecActiveConfig** commands.
You can use **Restore-SbecActiveConfig** to restore them.

This command returns a hash table with the elements `<OriginalTimestamp>` and `<Files>`.
The `<OriginalTimestamp>` element contains the original timestamp (that is, the time it was originally set) of the current active configuration.
You can compare it to the timestamps of the backup files to determine which configuration is active, and which configurations would be restored with the Undo and Redo commands.
It is in the binary FILETIME format, as are the timestamps in the other Sbec commands.

You can convert the binary FILETIME format to the PowerShell time with this code: `\[DateTime\]::FromFileTimeUtc($filetime)`

You can convert the PowerShell time to the FILETIME format with this code: `$datetime.ToFileTimeUtc()`

You can convert the PowerShell time (if it is marked as UTC time) to the timestamp format used in the names of the configuration backup files with this code: `$datetime.ToString("yyyyMMddHHmmssfffffff")`

The reverse conversion can be done with this code: `\[DateTime\]::ParseExact($fnametm, "yyyyMMddHHmmssfffffff", $null, "AssumeUniversal, AdjustToUniversal")`

To check whether a PowerShell time is marked as UTC time, use this code: `$datetime.Kind -eq "Utc"`

You can convert a PowerShell time in the local representation to the UTC representation with this code: `\[DateTime\]::FromFileTimeUtc($datetime.ToFileTimeUtc())`

The `<Files>` element contains an array of entries describing the available backup files.
Each entry is a hash with fields Name (containing the file name), Timestamp containing its original timestamp in the FILETIME format, and Time containing its original timestamp converted to the PowerShell DateTime format in local time, for convenience.
The entries in the array are ordered from the most recent to the oldest.

You must have Builtin Administrator privilege to run this command.

## EXAMPLES

### Example 1: Get available backup configuration files
```
PS C:\> Get-SbecBackupConfig | Format-List
```

This command gets the list of available backup configuration files and uses the pipeline operator to pass them to Format-List.

## PARAMETERS

### -CimSession
Runs the cmdlet on the remote computers through a remote session.
Enter a session object, such as the output of a **New-CimSession** or **Get-CimSession** cmdlet, or an array of these objects.
The default is to run the cmdlet on the local computer.
For more information, see About_CimSession.

```yaml
Type: CimSession[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
Specifies the names of the computers on which you want to perform the operation.
You can specify a fully qualified domain name (FQDN), a NetBIOS name, or an IP address for each computer.
For more information see [Invoke-CimMethod](https://go.microsoft.com/fwlink/?LinkId=808801) on MSDN.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None.

## OUTPUTS

### hash table
This cmdlet returns a hash table with two elements:

- `<OriginalTimestamp>`
- `<Files>`

The `<OriginalTimestamp>` element contains the original timestamp (that is, the time it was originally set) of the current active configuration in FILETIME format.

The `<Files>` element contains an array of entries describing the available backup files.
Each entry is a hash with fields:

- `<Name>`
- `<Timestamp>`
- `<Time>`

`<Name>` contains the file name, `<Timestamp>` contains its original timestamp in the FILETIME format, and `<Time>` contains its original timestamp converted to the PowerShell DateTime format in local time, for convenience.
The entries in the array are ordered from the most recent to the oldest.

## NOTES

## RELATED LINKS

[Checkpoint-SbecActiveConfig](./Checkpoint-SbecActiveConfig.md)

[Redo-SbecActiveConfig](./Redo-SbecActiveConfig.md)

[Restore-SbecBackupConfig](./Restore-SbecBackupConfig.md)

[Undo-SbecActiveConfig](./Undo-SbecActiveConfig.md)

