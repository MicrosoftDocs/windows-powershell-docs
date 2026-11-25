---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: BootEventCollector-help.xml
Module Name: BootEventCollector
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/booteventcollector/get-sbecactiveconfig?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-SbecActiveConfig
---

# Get-SbecActiveConfig

## SYNOPSIS
Gets the current active configuration from the running Setup and Boot Event Collector.

## SYNTAX

```
Get-SbecActiveConfig [[-ComputerName] <String[]>] [[-CimSession] <CimSession[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SbecActiveConfig** cmdlet returns a hash table with two elements, `<Content>` and `<Timestamp>`.
The `<Content>` element contains the text of the active configuration as a single string.
The `<Timestamp>` element contains the timestamp when that configuration was set, as a FILETIME 64-bit value.

You can use the timestamp to verify that the configuration didn't change since the last reading.
You can also use it to get the configuration, modify it locally, and set it back, and ensuring that nobody has modified it during that time.

You can modify the text of the configuration from the exact text that was last set.
You can normalize it by removing all the carriage return (`\r`) characters and by removing any empty lines at the end of configuration.

This command throws an error on failures.

This command is available only to the users having the Builtin Administrator (BA) privilege.

## EXAMPLES

### Example 1: Get the active configuration
```
PS C:\> $res = Get-SbecActiveConfig
```

This command gets the active configuration, and then stores it in the $res variable.

### Example 2: Convert a timestamp
```
PS C:\> $time = [DateTime]::FromFileTimeUtc($res.Timestamp)
```

This command converts the returned timestamp to the PowerShell format, and then stores it in the $res variable.

### Example 3: Get the text of a configuration
```
PS C:\> $text = $res.Content
```

This command extracts the returned text of the configuration as a single string, and then stores it in the $text variable.

### Example 4: Print the complete returned information
```
PS C:\> Get-SbecActiveConfig | Format-List
```

This command gets the active configuration and pipes it to Format-List, which formats the results.

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
For more information see [Invoke-CimMethod](https://go.microsoft.com/fwlink/?LinkId=808801) on TechNet.

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

- `<Content>`
- `<Timestamp>`

The `<Content>` element contains the text of the active configuration as a single string.
The `<Timestamp>` element contains the timestamp when that configuration was set, as a FILETIME 64-bit value.
The common way to see the full result is to pipe it through the **Format-List** cmdlet (alias fl).

## NOTES

## RELATED LINKS

[Set-SbecActiveConfig](./Set-SbecActiveConfig.md)

[Test-SbecActiveConfig](./Test-SbecActiveConfig.md)

[Test-SbecConfig](./Test-SbecConfig.md)

