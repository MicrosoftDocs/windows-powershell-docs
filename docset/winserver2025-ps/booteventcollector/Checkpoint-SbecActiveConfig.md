---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: BootEventCollector-help.xml
Module Name: BootEventCollector
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/booteventcollector/checkpoint-sbecactiveconfig?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Checkpoint-SbecActiveConfig
---

# Checkpoint-SbecActiveConfig

## SYNOPSIS
Creates a configuration checkpoint.

## SYNTAX

```
Checkpoint-SbecActiveConfig [[-OldTimestamp] <UInt64>] [-Continue] [[-ComputerName] <String[]>]
 [[-CimSession] <CimSession[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Checkpoint-SbecActiveConfig** cmdlet creates a checkpoint for the active Boot Event Collector configuration.

The checkpoint enables you to return to this configuration later using the **Undo-SbecActiveConfig**, **Redo-SbecActiveConfig**, and **Restore-SbecBackupConfig** cmdlets.
The checkpoints mark the known good configurations that you can revert to if a new configuration is incorrect.
For example, if you changed a configuration yesterday, find an issue with it today, and want to revert to yesterday's configuration before you made a change, you can use the checkpointed configuration from yesterday.

Most checkpoints are created automatically, but on rare occasions you might need to explicitly create them.
Automatic checkpoints are created when the current configuration has not yet been checkpointed and one of the following events occurs:

- The Collector service is restarted.
- The configuration that was running for more than an hour is replaced with another configuration.
In this case, the old configuration is checkpointed before being replaced.
- A new configuration is set with **Set-SbecActiveConfig**.
This new configuration is immediately checkpointed.

A checkpoint ensures that the current configuration is remembered, but it doesn't immediately create a backup configuration file.
Instead, the checkpointed current configuration is saved to a backup file when the configuration changes.

The repeated checkpointing succeeds but has no effect, because it only flags the configuration to create a backup in the future.

The **Undo-SbecActiveConfig**, **Redo-SbecActiveConfig**, and **Restore-SbecBackupConfig** cmdlets change the current configuration by browsing through the backup configurations, but they don't do an immediate checkpointing.
This lets you browse through the past configurations, try them out, and change your mind if a configuration doesn't work well without causing a flurry of spurious checkpoints and backup files with identical content.
When you are satisfied with a configuration, checkpoint it with **Checkpoint-SbecActiveConfig**.
If you forget to create a checkpoint for a configuration, it is automatically checkpointed after an hour.

Use **Get-SbecBackupConfig** to get the list of backup configuration files.

You can use the *OldTimestamp* parameter to modify the configuration atomically.

You must have the Builtin Administrator rights to run the cmdlet.

## EXAMPLES

### Example 1: Undo a configuration and create a checkpoint
```
PS C:\> Undo-SbecActiveConfig | Format-List; Checkpoint-SbecActiveConfig | Format-List
```

This command undoes a configuration and creates a checkpoint, in a simple way.
**Format-List** formats the information that this cmdlet returns.

### Example 2: Undo a configuration and create a checkpoint atomically
```
PS C:\> $res = Undo-SbecActiveConfig | Format-List
PS C:\> $res = Checkpoint-SbecActiveConfig -OldTimestamp $res.OriginalTimestamp | Format-LIst
```

This command undoes a configuration and creates a checkpoint, making sure that no other changes are done in between, and throwing on errors.

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
Indicates that this operation will not throw an exception if a failure occurs.
Instead, the caller should examine the output of the cmdlet for the error information.

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
This operation checks that the *OldTimestamp* value matches either the normal or original timestamp of the current active configuration, thus ensuring that the active configuration has not changed since the last time you examined it.
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

## OUTPUTS

### hashtable
This cmdlet returns a hashtable that includes the following elements:

- `<Success>`
- `<ErrorType>`
- `<ErrorString>`
- `<WarningString>`
- `<InfoString>`

The Success element is $True on success, $False otherwise.
You can use the *Continue* parameter to not throw an error on failure.

The `<ErrorType>` element contains 0 on success.
If a failure occurs, `<ErrorType>` has a code that describes the error:

- 1 - Bad argument format.
- 2 - Bad argument value.
- 3 - Resource (socket) open error.
- 4 - Persistence (backup configuration file) error.
- 5 - Atomicity error (that is, the old timestamp does not match).

`<ErrorString>`, `<WarningString>`, and `<InfoString>` contain detailed error messages.
`<ErrorString>` contains information only if an error occurs.

## NOTES

## RELATED LINKS

[Get-SbecBackupConfig](./Get-SbecBackupConfig.md)

[Redo-SbecActiveConfig](./Redo-SbecActiveConfig.md)

[Restore-SbecBackupConfig](./Restore-SbecBackupConfig.md)

[Set-SbecActiveConfig](./Set-SbecActiveConfig.md)

[Undo-SbecActiveConfig](./Undo-SbecActiveConfig.md)

