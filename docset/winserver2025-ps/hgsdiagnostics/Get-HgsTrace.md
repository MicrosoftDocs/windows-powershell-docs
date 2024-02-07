---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Windows.HostGuardianService.Diagnostics.Payload.dll-Help.xml
Module Name: HgsDiagnostics
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hgsdiagnostics/get-hgstrace?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-HgsTrace
---

# Get-HgsTrace

## SYNOPSIS
Collects and analyzes data relevant to the operation of a guarded fabric.

## SYNTAX

### Collect (Default)
```
Get-HgsTrace [-Collector <String[]>] [-Target <InputTarget[]>] [[-Path] <String>] [-WriteManifest] [-Detailed]
 [-Compact] [-Diagnostic <String[]>] [<CommonParameters>]
```

### Diagnose
```
Get-HgsTrace [-RunDiagnostics] [-Target <InputTarget[]>] [[-Path] <String>] [-WriteManifest] [-Detailed]
 [-Compact] [-Diagnostic <String[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-HgsTrace** cmdlet collects and analyzes data relevant to the operation of a guarded fabric, diagnosing confirmed and potential failures in the environment that will impact the operation of the Host Guardian Service (HGS), guarded hosts, and shielded virtual machines.

## EXAMPLES

### Example 1: Diagnose the local host
```
PS C:\> Get-HgsTrace -RunDiagnostics
```

This command diagnoses the local host.
The traces are stored in a temporary folder and diagnosis results are reported to the user.

### Example 2: Collect traces from the specified target
```
PS C:\> Get-HgsTrace -Target $VMhost -Path ".\Traces"
```

This command collects traces from the target specified in the VMhost variable.
The command then stores the trace files to the specified path.
Since the *RunDiagnostics* parameter is not used, the cmdlet does not run diagnostics against the collected targets.

### Example 3: Diagnose multiple targets
```
PS C:\> Get-HgsTrace -Target $VMhost,$Server -RunDiagnostics
```

This command runs diagnostics on the targets stored in the $VMHost and $Server variables.

### Example 4: Diagnose the local host using hardware
```
PS C:\> Get-HgsTrace -RunDiagnostics -Diagnostic "Hardware"
```

This command runs diagnostics named Hardware on the local host.

### Example 5: Diagnose previously collected traces stored in the specified folder
```
PS C:\> Get-HgsTrace -RunDiagnostics -Path ".\GatheredTraces"
```

This command runs diagnostics on collected traces that are stored in the folder named GatheredTraces.

## PARAMETERS

### -Collector
Specifies a list of collectors to be executed when gathering traces.
This parameter is used to collect only specific traces when you do not specify a list of diagnostics and you do not run diagnostics with the *RunDiagnostics* switch.

```yaml
Type: String[]
Parameter Sets: Collect
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Compact
Indicates that the output object is provided should be a minimal subset of the results generated instead of the complete result set.
This switch parameter is ignored if more than one target is provided.

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

### -Detailed
Specifies that the output object has full details, which includes all results omitted from the default output report.

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

### -Diagnostic
Specifies a list of diagnostics that are run if you also provide the *RunDiagnostics* switch parameter.
If you do not provide the *RunDiagnostics* switch parameter, this list of diagnostics is used to determine which collectors are executed.
Diagnostics and collectors whose requirements are not satisfied by the provided targets will not be executed.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:
Accepted values: Base, All, GuardedFabric, GuardedFabricTpmMode, GuardedFabricADMode, BestPractices, GuardedHost, HostGuardianService, Networking, Https, Hardware

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path
Specifies an absolute or relative path to a folder where trace files are stored.
If the folder already exists, any traces contained therein are reused.
New traces are collected to augment existing traces if they are missing from the pre-populated traces.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RunDiagnostics
Indicates that diagnostics are immediately run against the collected traces and that the result set describes the result of diagnosing the collected information.

```yaml
Type: SwitchParameter
Parameter Sets: Diagnose
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Target
Specifies a list of targets created by **New-HgsTraceTarget** to be traced and diagnosed.
If no targets are provided, but a collection path has been specified, the path is searched for pre-existing traces to be analyzed.
If none are found, the localhost is targeted using the current session's credentials inferring the host's role from installed Windows features.

```yaml
Type: InputTarget[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -WriteManifest
Indicates that a manifest of all trace files collected are written.
This can then be used by the **Get-HgsTraceFileData** cmdlet to get secured information about trace files.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Windows.HostGuardianService.Diagnostics.Payload.InputTarget
This cmdlet pipes one or more targets created with **New-HgsTraceTarget** to trace and diagnose.

## OUTPUTS

### Microsoft.Windows.HostGuardianService.Diagnostics.Payload.RemoteResultSet
This cmdlet returns a collection of results for various operations and tests performed on the provided targets.
These results are grouped by target and category with each group possessing an aggregate result that reflects the status of all child operation.

## NOTES

## RELATED LINKS

[Get-HgsTraceFileData](./Get-HgsTraceFileData.md)

[New-HgsTraceTarget](./New-HgsTraceTarget.md)

