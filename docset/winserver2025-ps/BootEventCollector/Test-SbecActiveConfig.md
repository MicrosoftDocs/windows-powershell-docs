---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: BootEventCollector-help.xml
Module Name: BootEventCollector
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/booteventcollector/test-sbecactiveconfig?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Test-SbecActiveConfig
---

# Test-SbecActiveConfig

## SYNOPSIS
Tests the active Boot Event Collector configuration.

## SYNTAX

```
Test-SbecActiveConfig [-Content] <String[]> [[-ComputerName] <String[]>] [[-CimSession] <CimSession[]>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Test-SbecActiveConfig** cmdlet tests whether the specified Boot Event Collector configuration matches the current active configuration.

The comparison is done on the "normalized" text of the configuration by removing all the carriage return (`\r`) characters and by removing any empty lines at the end of configuration.
The empty lines in the middle of the text are not removed, and the white space matters.

This command returns $True if the configurations match; otherwise, it returns $False.

This command throws an error on failures.

You must have the Builtin Administrator privilege to run this command.

## EXAMPLES

### Example 1: Test a configuration file through a pipeline
```
PS C:\> Get-Content -Path "c:\MyConfig.xml" | Test-SbecActiveConfig
```

This command compares the current configuration with the contents of the file MyConfig.xml by passing it through a pipeline.

### Example 2: Test a configuration file through a parameter
```
PS C:\> Test-SbecActiveConfig -Content "(Get-Content -Path "c:\MyConfig.xml")"
```

This command compares the current configuration with the contents of the file MyConfig.xml by passing it as a parameter.

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

### -Content
Specifies the configuration to test.
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### string
The text of the configuration, same as in the *Content* parameter.

## OUTPUTS

### Boolean
The result of comparison: $True or $False.

## NOTES

## RELATED LINKS

[Get-SbecActiveConfig](./Get-SbecActiveConfig.md)

[Set-SbecActiveConfig](./Set-SbecActiveConfig.md)

[Test-SbecConfig](./Test-SbecConfig.md)

