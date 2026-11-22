---
external help file: DDVCmdlets.dll-Help.xml
Module Name: Microsoft.DiagnosticDataViewer
online version: https://learn.microsoft.com/powershell/module/microsoft.diagnosticdataviewer/get-diagnosticstorecapacity?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-DiagnosticStoreCapacity
---

# Get-DiagnosticStoreCapacity

## SYNOPSIS
Fetches the current diagnostic store capacity.
Parameter \[-Size\] returns the diagnostic store size capacity in megabytes.
Parameter \[-Time\] returns the diagnostic store capacity in days.
The default diagnostic data store size capacity is 1024 MB.
The default time capacity is 30 days.

## SYNTAX

```
Get-DiagnosticStoreCapacity [-Size] [-Time] [<CommonParameters>]
```

## DESCRIPTION
The amount of Diagnostic Data history that can be shown through this tool is capped based on time in days and size in megabytes.
Once either cap is reached (whichever comes first), diagnostic data is removed based on a first in first out order.
For example, if the size cap is 1GB and the time cap is 30 days, then once the diagnostic data store has reached 1GB of history or the oldest record is 30 days old (whichever comes first), the oldest seen event is dropped.

## EXAMPLES

### EXAMPLE 1
```
Get-DiagnosticStoreCapacity -Size
```

Get configured size capacity (megabytes) of the Diagnostic store.

### EXAMPLE 2
```
Get-DiagnosticStoreCapacity -Time
```

Get configured time capacity (hours) of the Diagnostic store.

## PARAMETERS

### -Size
Get configured size capacity (megabytes) of the Diagnostic store.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: s

Required: False
Position: Named
Default value: False
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Time
Get configured time capacity (hours) of the Diagnostic store.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: t

Required: False
Position: Named
Default value: False
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.Management.Automation.SwitchParameter
Get configured size capacity (megabytes) of the Diagnostic store.

### System.Management.Automation.SwitchParameter
Get configured time capacity (hours) of the Diagnostic store.

## OUTPUTS

### System.String
## NOTES
Requires Windows 10 version 17134 (1803) or higher

## RELATED LINKS
