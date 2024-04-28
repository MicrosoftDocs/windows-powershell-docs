---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: BootEventCollector-help.xml
Module Name: BootEventCollector
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/booteventcollector/set-sbecactiveconfig?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-SbecActiveConfig
---

# Set-SbecActiveConfig

## SYNOPSIS
Sets the new active configuration for the running Setup and Boot Event Collector.

## SYNTAX

```
Set-SbecActiveConfig [-Content] <String[]> [[-OldTimestamp] <UInt64>] [-Continue] [[-ComputerName] <String[]>]
 [[-CimSession] <CimSession[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-SbecActiveConfig** cmdlet sets the new active configuration for the running Setup and Boot Event Collector.

The new configuration is checked for validity, and on success is applied to both the running collector instance and its active configuration file, so that the configuration is remembered and used even after the system restarts.
The previous configuration is saved in a backup file, which enables you to undo any changes.

You can use Get-SbecActiveConfig and **Set-SbecActiveConfig** to modify the configuration atomically, as follows:

1. Get the old configuration text and timestamp with **Get-SbecActiveConfig**.
2. Modify the configuration text.
3. Pass the text and timestamp (using the *OldTimestamp* parameter) to **Set-SbecActiveConfig**.

If the *OldTimestamp* parameter is specified, the Collector checks whether the active configuration was changed in between.

If this check succeeds, the new configuration is applied; otherwise, an error is returned.

If the previous configuration was restored from a backup file (for example, by Undo-SbecActiveConfig), it also has the original timestamp when that configuration was originally set, and its normal timestamp is the time when it was restored.
You can use Get-SbecBackupConfig to get the original timestamp.
For such a configuration, the OldTimestamp parameter of **Set-SbecActiveConfig** may match either the normal or original timestamp of the previous configuration.

The text of the configuration becomes normalized before the configuration is set by removing all the carriage return (`\r`) characters and by removing any empty lines at the end of configuration.
The carriage return characters are inserted appropriately when the configuration is saved to the file for persistence.

You must have Builtin Administrator privilege to run this cmdlet.

## EXAMPLES

### Example 1: Set the active configuration
```
PS C:\> Set-SbecActiveConfig -Content $NewConfig | Format-List
```

This command sets the configuration and throws on error.
Format-List formats the returned information.

### Example 2: Set the active configuration from a file
```
PS C:\> Get-Content MyConfig.xml | Set-SbecActiveConfig -Continue | Format-List
```

This command sets the configuration and does not throw on error.
Format-List formats the returned information.

### Example 3: Set the configuration as an atomic modification
```
PS C:\> do { $prev = Get-SbecActiveConfig; $res = Set-SbecActiveConfig -Content (Modify-MyConfig $prev.Content) -OldTimestamp $prev.Timestamp -Continue } while ($res.ErrorType -eq 5); if ($res.Success) { ... } else { ... }
```

This command sets the new configuration as an atomic modification of the previous configuration.

If the atomicity is broken, the code re-tries by getting the new configuration and modifying it again.

## PARAMETERS

### -CimSession
Runs the cmdlet on the remote computers through a remote session.
Enter a session object, such as the output of a **New-CimSession** or **Get-CimSession** cmdlet or an array of these objects.
The default is to run the cmdlet on the local computer.
For more information, see About_CimSession.

```yaml
Type: CimSession[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
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
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Content
Specifies the configuration to set as active.
The acceptable values for this parameter are:

- A multiline string.
Use `\n` to indicate line breaks.
- An array of one-line strings.
This cmdlet merges the array.
- A mix of multiline strings and string arrays.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
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
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### string[]
The text of the configuration, same as in the *Content* parameter.

## OUTPUTS

### hash table
The hash table includes the following elements:

- Success
- NewTimestamp
- ErrorType
- ErrorString
- WarningString
- InfoString

The `<ErrorType>` element contains 0 on success.
If a failure occurs, `<ErrorType>` has a code that describes the error:

- 1 (bad argument format)
- 2 (bad argument value)
- 3 (resource (socket) open error)
- 4 (persistence (backup configuration file) error)
- 5 (atomicity error (that is, the old timestamp does not match)

The Success element is $True on success, $False otherwise.

The `<NewTimeStamp>` element contains the timestamp of the newly restored configuration, that is, the time when it was restored, if this operation is successful, the current original timestamp if the timestamp check fails, or $Null on other failures.

ErrorString, WarningString, and InfoString contain detailed error messages.
`<ErrorString>` contains information only if an error occurs.

## NOTES

## RELATED LINKS

[Get-SbecActiveConfig](./Get-SbecActiveConfig.md)

[Restore-SbecBackupConfig](./Restore-SbecBackupConfig.md)

[Test-SbecActiveConfig](./Test-SbecActiveConfig.md)

[Test-SbecConfig](./Test-SbecConfig.md)

[Undo-SbecActiveConfig](./Undo-SbecActiveConfig.md)

