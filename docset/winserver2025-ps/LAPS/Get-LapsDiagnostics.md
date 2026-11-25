---
description: Collects Windows Local Administrator Password Solution (LAPS) logs and tracing from the local machine.
external help file: LAPS-help.xml
Module Name: LAPS
online version: https://learn.microsoft.com/powershell/module/laps/get-lapsdiagnostics?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
Locale: en-US
ms.date: 04/10/2023
title: Get-LapsDiagnostics
---

# Get-LapsDiagnostics

## SYNOPSIS
Collects Windows Local Administrator Password Solution (LAPS) logs and tracing from the local
machine.

## SYNTAX

```
Get-LapsDiagnostics [[-OutputFolder] <String>] [-CollectNetworkTrace] [-ResetPassword]
 [<CommonParameters>]
```

## DESCRIPTION

The `Get-LapsDiagnostics` cmdlet collects LAPS logs and tracing from the local machine, and copies
them into a `.zip` file. This cmdlet is primarily intended for support and testing scenarios but of
course may be used at any time. The name of the resultant `.zip` file includes the machine name and
current timestamp, and by default is written under the `$env:TEMP\LapsDiagnostics` folder. The
output folder may be customized using the **OutputFolder**.

## EXAMPLES

### Example 1

```powershell
Get-LapsDiagnostics
```

```Output
Get-LapsDiagnostics: all data for this run was written to the following zip file:

C:\Users\ADMINI~1\AppData\Local\Temp\LapsDiagnostics\LapsDiagnostics_LAPSCLIENT_2023041004_072649.zip
```

This example demonstrates basic collection of LAPS diagnostic info using all default parameters.

### Example 2

```powershell
Get-LapsDiagnostics -OutputFolder c:\LapsDiagFolder
```

```Output
Get-LapsDiagnostics: all data for this run was written to the following zip file:

c:\LapsDiagFolder\LapsDiagnostics_LAPSCLIENT_2023041004_072702.zip
```

This example demonstrates basic collection of LAPS diagnostic info to a specific output folder.

### Example 3

```powershell
Get-LapsDiagnostics -OutputFolder c:\LapsDiagFolder -ResetPassword
```

```Output
Get-LapsDiagnostics: all data for this run was written to the following zip file:

c:\LapsDiagFolder\LapsDiagnostics_LAPSCLIENT_2023041004_072709.zip
```

This example demonstrates basic collection of LAPS diagnostic info across a forced password reset
operation to a specific output folder.

### Example 4

```powershell
Get-LapsDiagnostics -CollectNetworkTrace
```

```Output
Get-LapsDiagnostics: all data for this run was written to the following zip file:

C:\Users\ADMINI~1\AppData\Local\Temp\LapsDiagnostics\LapsDiagnostics_LAPSCLIENT_2023041004_072719.zip
```

This example demonstrates basic collection of LAPS diagnostic info while also collecting network
tracing.

## PARAMETERS

### -CollectNetworkTrace

Specifies that network tracing should also be collected and included in the resultant `.zip` file.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OutputFolder

Specifies that the resultant `.zip` file should be placed under the specified folder.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResetPassword

Specifies that logs and tracing should be collected across a forced password reset for the currently
managed local account. In this mode the cmdlet collects tracing across a call to the
`Reset-LapsPassword` cmdlet.

If this parameter isn't specified, the cmdlet collects tracing across a call to the
`Invoke-LapsProcessingCycle` cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Windows LAPS Overview](https://go.microsoft.com/fwlink/?linkid=2233901)
