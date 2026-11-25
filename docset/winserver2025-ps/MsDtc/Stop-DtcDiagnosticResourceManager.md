---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Dtc.PowerShell.dll-Help.xml
Module Name: MsDtc
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/msdtc/stop-dtcdiagnosticresourcemanager?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-DtcDiagnosticResourceManager
---

# Stop-DtcDiagnosticResourceManager

## SYNOPSIS
Stops and removes a diagnostic Resource Manager job.

## SYNTAX

### ParameterSetInstance (Default)
```
Stop-DtcDiagnosticResourceManager [[-Job] <DtcDiagnosticResourceManagerJob>] [<CommonParameters>]
```

### ParameterSetName
```
Stop-DtcDiagnosticResourceManager [[-Name] <String>] [<CommonParameters>]
```

### ParameterSetInstanceId
```
Stop-DtcDiagnosticResourceManager [[-InstanceId] <Guid>] [<CommonParameters>]
```

## DESCRIPTION
The **Stop-DtcDiagnosticResourceManager** cmdlet stops and removes a **DiagnosticResourceManagerJob** that runs as a Windows PowerShell® background job.
To stop the default Resource Manager, you must explicitly specify the name of the default Resource Manager.

## EXAMPLES

### Example 1: Stop a diagnostic resource manager
```
PS C:\> Stop-DtcDiagnosticResourceManager -Name "testRM"
```

This command stops the DTC diagnostic resource manager named testRM.

## PARAMETERS

### -InstanceId
Specifies the **DtcDiagResourceManagerJob** instance ID to stop.

```yaml
Type: Guid
Parameter Sets: ParameterSetInstanceId
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Job
Specifies the **DtcDiagResourceManagerJob** instance to stop.
This parameter accepts pipeline input.

```yaml
Type: DtcDiagnosticResourceManagerJob
Parameter Sets: ParameterSetInstance
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Specifies a name of the diagnostic resource manager to stop.

```yaml
Type: String
Parameter Sets: ParameterSetName
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

## NOTES

## RELATED LINKS

[Join-DtcDiagnosticResourceManager](./Join-DtcDiagnosticResourceManager.md)

[Start-DtcDiagnosticResourceManager](./Start-DtcDiagnosticResourceManager.md)

