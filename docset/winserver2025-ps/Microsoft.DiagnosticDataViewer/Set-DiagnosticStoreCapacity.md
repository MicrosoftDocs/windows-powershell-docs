---
external help file: DDVCmdlets.dll-Help.xml
Module Name: Microsoft.DiagnosticDataViewer
online version: https://learn.microsoft.com/powershell/module/microsoft.diagnosticdataviewer/set-diagnosticstorecapacity?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-DiagnosticStoreCapacity
---

# Set-DiagnosticStoreCapacity

## SYNOPSIS
Sets the diagnostic store time and size capacity.

## SYNTAX

```
Set-DiagnosticStoreCapacity [[-Size] <UInt32>] [[-Time] <UInt32>] [<CommonParameters>]
```

## DESCRIPTION
This cmdlet sets the maximum amount of Diagnostic Data history (by time and by size) that can be shown through this tool.
The size cap is measured in megabytes, and the time cap is measured in days.
Once the either cap is reached (whichever comes first), diagnostic data history is removed based on a first in first out order.

## EXAMPLES

### EXAMPLE 1
```
Set-DiagnosticStoreCapacity -Size 1024
```

Set store capacity (megabytes) of the diagnostic store.

### EXAMPLE 2
```
Set-DiagnosticStoreCapacity -Time 24
```

Set time capacity (hours) of the diagnostic store.

### EXAMPLE 3
```
Set-DiagnosticStoreCapacity -Size 1024 -Time 24
```

Set store capacity (megabytes) and time capacity (hours) of the diagnostic store at the same time.

## PARAMETERS

### -Size
Set size capacity of the diagnostic store.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: s

Required: False
Position: 0
Default value: 0
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Time
Set time capacity of the diagnostic store.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: t

Required: False
Position: 1
Default value: 0
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.UInt32
Set size capacity of the diagnostic store.

### System.UInt32
Set time capacity of the diagnostic store.

## OUTPUTS

### System.String
## NOTES
Requires Windows 10 version 17134 (1803) or higher

## RELATED LINKS
