---
external help file: MsDTC_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: 5ACAD949-DA35-4E3B-97AF-3AA9FB44A307
manager: dansimp
---

# Stop-DtcDiagnosticResourceManager

## SYNOPSIS
Stops and removes a diagnostic Resource Manager job.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Stop-DtcDiagnosticResourceManager [[-Job] <DtcDiagnosticResourceManagerJob>]
```

### UNNAMED_PARAMETER_SET_2
```
Stop-DtcDiagnosticResourceManager [[-InstanceId] <Guid>]
```

### UNNAMED_PARAMETER_SET_3
```
Stop-DtcDiagnosticResourceManager [[-Name] <String>]
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
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Job
Specifies the **DtcDiagResourceManagerJob** instance to stop.
This parameter accepts pipeline input.

```yaml
Type: DtcDiagnosticResourceManagerJob
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Specifies a name of the diagnostic resource manager to stop.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Join-DtcDiagnosticResourceManager](./Join-DtcDiagnosticResourceManager.md)

[Start-DtcDiagnosticResourceManager](./Start-DtcDiagnosticResourceManager.md)

