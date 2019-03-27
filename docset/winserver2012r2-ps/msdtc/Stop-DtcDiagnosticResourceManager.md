---
external help file: Microsoft.Dtc.PowerShell.dll-Help.xml
Module Name: MsDtc
online version: 
schema: 2.0.0
title: Stop-DtcDiagnosticResourceManager
description: 
keywords: powershell, cmdlet
author: kenwith
manager: jasgro
ms.date: 2017-10-29
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 5ACAD949-DA35-4E3B-97AF-3AA9FB44A307
ms.author: kenwith
ms.reviewer: brianlic
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
PS C:\>Stop-DtcDiagnosticResourceManager -Name "testRM"
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Join-DtcDiagnosticResourceManager](./Join-DtcDiagnosticResourceManager.md)

[Start-DtcDiagnosticResourceManager](./Start-DtcDiagnosticResourceManager.md)

