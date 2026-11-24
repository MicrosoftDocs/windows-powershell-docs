---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: BootEventCollector-help.xml
Module Name: BootEventCollector
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/booteventcollector/restore-sbecbackupconfig?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Restore-SbecBackupConfig
---

# Restore-SbecBackupConfig

## SYNOPSIS
Restores a configuration from a backup file.

## SYNTAX

### Name
```
Restore-SbecBackupConfig -Name <String> [-OldTimestamp <UInt64>] [-Continue] [-ComputerName <String[]>]
 [-CimSession <CimSession[]>] [<CommonParameters>]
```

### At
```
Restore-SbecBackupConfig -At <Object> [-OldTimestamp <UInt64>] [-Continue] [-ComputerName <String[]>]
 [-CimSession <CimSession[]>] [<CommonParameters>]
```

### AtTimestamp
```
Restore-SbecBackupConfig -AtTimestamp <UInt64> [-OldTimestamp <UInt64>] [-Continue] [-ComputerName <String[]>]
 [-CimSession <CimSession[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Restore-SbecBackupConfig** cmdlet restores a Boot Event Collector configuration from a backup file.

If the previous active configuration was not itself restored but set afresh (or checkpointed after restore), it is saved in a backup file.
When doing multiple undo/redo/restore commands in a sequence, the intermediate configurations are not saved in the new backup files.
A configuration from undo/redo/restore commands is automatically considered checkpointed if it was left unchanged for an hour.

You can use the OldTimestamp parameter to modify the configuration atomically.

The restored configuration is re-checked for validity, and refused if it has become corrupted.

You must have Builtin Administrator privilege to run this cmdlet.

## EXAMPLES

### Example 1: Restore a backup configuration by name
```
PS C:\> Restore-SbecBackupConfig -Name "Active.xml.201502202002352592047.xml" | Format-List
```

This command restores the backup file named Active.xml.201502202002352592047.xml and uses the pipeline operator to pass it to Format-List, which formats the hash table returned by the operation.

### Example 2: Restore the most recent backup configuration
```
PS C:\> $res = Restore-SbecBackupConfig -Name ((Get-SbecBackupConfig).Files[0].Name)
```

This command restores the most recent backup file from the list of available ones, identifying it by name.

### Example 3: Restore a backup based on its time
```
PS C:\> $res = Restore-SbecBackupConfig -At ((Get-SbecBackupConfig).Files[0].Time)
```

This command restores the most recent backup file from the list of available backups, and identifies it by its time.

### Example 4: Restore a backup based on its FILETIME timestamp
```
PS C:\> $Res = Restore-SbecBackupConfig -AtTimestamp ((Get-SbecBackupConfig).Files[0].Timestamp)
```

This command restores the most recent backup file from the list of available ones, identifying it by the FILETIME timestamp.

### Example 5: Restore a configuration from a specified time
```
PS C:\> $res = Restore-SbecBackupConfig -At 20150219
```

This command restores the backup configuration that was active at midnight UTC of February 19 2015.

## PARAMETERS

### -At
Specifies the timestamp of the configuration file to restore.
The acceptable values for this parameter are:

- A **DateTime** object.
- A string.
- A number.
Use the format YYYYMMDDhhmmssfffffff, where f represents the fractions of a second.
---- Values for YYYYMMDD are required.
---- If you don't specify a value for hours, minutes, or seconds, this cmdlet appends zeros for those values.
For example, this cmdlet interprets 201502012033 as February 1st 2015 20:33:00.

See Get-SbecBackupConfig for more information about timestamp formats and how to convert them.

```yaml
Type: Object
Parameter Sets: At
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AtTimestamp
Specifies a FILETIME timestamp of the configuration file to restore.

See Get-SbecBackupConfig for more information about timestamp formats and how to convert them.

```yaml
Type: UInt64
Parameter Sets: AtTimestamp
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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
Position: Named
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
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Continue
Specifies that this operation will not throw an exception if a failure occurs.
Instead the caller should examine the output of the cmdlet for the error information.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the configuration file to restore.
To get the list of backup configuration files, use the Get-SbecBackupConfig cmdlet.

```yaml
Type: String
Parameter Sets: Name
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OldTimestamp
Specifies the timestamp of the previous active configuration.
This provides a way to perform the atomic changes of the configuration.
Each configuration has a timestamp (the time when it was last set or restored) and an original timestamp (if the configuration was restored, the time when it was originally set, otherwise the same as the normal timestamp).
This operation checks that the *OldTimestamp* value matches either the normal or original timestamp of the current active configuration, thus ensuring that the active configuration wasn't changed since the last time you have looked at it.
If the values do not match, an error is returned.

```yaml
Type: UInt64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None.

## OUTPUTS

### hashtable
The hashtable includes the following elements:

- `<Success>`
- `<NewTimestamp>`
- `<OriginalTimestamp>`
- `<ErrorType>`
- `<ErrorString>`
- `<WarningString>`
- `<InfoString>`

The `<ErrorType>` element contains 0 on success.
If a failure occurs, `<ErrorType>` has a code that describes the error:

- 1 (bad argument format)
- 2 (bad argument value)
- 3 (resource (socket) open error)
- 4 (persistence (backup configuration file) error)
- 5 (atomicity error (that is, the old timestamp does not match)

The Success element is $True on success, $False otherwise.

The `<NewTimeStamp>` element contains the timestamp of the newly restored configuration, i.e.
the time when it was restored, if this operation is successful, the current original timestamp if the timestamp check fails, or $Null on other failures.

The `<OriginalTimestamp>` element contains the original timestamp of the newly restored configuration on success, the current original timestamp on the timestamp check failure, or $Null on other failures.

`<ErrorString>`, `<WarningString>`, and `<InfoString>` contain detailed error messages.
`<ErrorString>` contains information only if an error occurs.

## NOTES

## RELATED LINKS

[Checkpoint-SbecActiveConfig](./Checkpoint-SbecActiveConfig.md)

[Get-SbecBackupConfig](./Get-SbecBackupConfig.md)

[Redo-SbecActiveConfig](./Redo-SbecActiveConfig.md)

[Set-SbecActiveConfig](./Set-SbecActiveConfig.md)

[Undo-SbecActiveConfig](./Undo-SbecActiveConfig.md)

