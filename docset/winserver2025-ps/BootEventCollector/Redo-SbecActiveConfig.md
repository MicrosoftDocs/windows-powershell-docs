---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: BootEventCollector-help.xml
Module Name: BootEventCollector
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/booteventcollector/redo-sbecactiveconfig?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Redo-SbecActiveConfig
---

# Redo-SbecActiveConfig

## SYNOPSIS
Redoes a change to the current active configuration.

## SYNTAX

```
Redo-SbecActiveConfig [[-OldTimestamp] <UInt64>] [-Continue] [[-ComputerName] <String[]>]
 [[-CimSession] <CimSession[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Redo-SbecActiveConfig** cmdlet redoes a change to the current active configuration.
This operation is the opposite of undoing a change to a configuration.

If multiple backup configuration files are available, you can apply Undo and Redo operations sequentially to move through the configurations backwards and forwards.

If the previous active configuration was not itself restored but set afresh (or checkpointed after restore), it is saved in a backup file.
When doing multiple undo/redo/restore commands in a sequence, the intermediate configurations are not saved in the new backup files.
A configuration from undo/redo/restore commands is automatically considered checkpointed if it was left unchanged for an hour.

You can use the *OldTimestamp* parameter to modify the configuration atomically.

The restored configuration is re-checked for validity, and refused if it has become corrupted.

You must have the Builtin Administrator privilege to run this command.

## EXAMPLES

### Example 1: Redo a configuration change
```
PS C:\> Redo-SbecActiveConfig -Continue | Format-List
```

This command redoes a configuration change.
Format-List displays the information that the command returns.

### Example 2: Redo two configuration changes
```
PS C:\> $res = Redo-SbecActiveConfig; $res = Redo-SbecActiveConfig -OldTimestamp $res.OriginalTimestamp
```

This command consecutively redoes two configuration changes, ensuring that no other changes are done in between, and throwing on errors.
This requires that the configuration was previously undone at least twice from the most recent one.

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
Position: 2
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
Position: 1
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

### -OldTimestamp
Specifies the timestamp of the previous active configuration.
This provides a way to perform the atomic changes of the configuration.
Each configuration has a timestamp (the time when it was last set or restored) and an original timestamp (if the configuration was restored, the time when it was originally set, otherwise the same as the normal timestamp).
This operation checks that the *OldTimestamp* value matches either the normal or original timestamp of the current active configuration thus ensuring that the active configuration wasn't changed since the last time you have looked at it.
If the values do not match, an error is returned.

```yaml
Type: UInt64
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
The hash table includes the following elements:

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

The `<NewTimeStamp>` element contains the timestamp of the newly restored configuration (that is, the time when it was restored) if this operation is successful, the current original timestamp if the timestamp check fails, or $Null on other failures.

The `<OriginalTimestamp>` element contains the original timestamp of the newly restored configuration on success, the current original timestamp on the timestamp check failure, or $Null on other failures.

`<ErrorString>`, `<WarningString>`, and `<InfoString>` contain detailed error messages.
`<ErrorString>` contains information only if an error occurs.

## NOTES

## RELATED LINKS

[Checkpoint-SbecActiveConfig](./Checkpoint-SbecActiveConfig.md)

[Get-SbecBackupConfig](./Get-SbecBackupConfig.md)

[Restore-SbecBackupConfig](./Restore-SbecBackupConfig.md)

[Set-SbecActiveConfig](./Set-SbecActiveConfig.md)

[Undo-SbecActiveConfig](./Undo-SbecActiveConfig.md)

