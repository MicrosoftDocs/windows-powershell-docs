---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.HyperV.PowerShell.Cmdlets.dll-Help.xml
Module Name: Hyper-V
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hyper-v/start-vmtrace?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Start-VMTrace
---

# Start-VMTrace

## SYNOPSIS
Starts tracing to a file.

## SYNTAX

```
Start-VMTrace [-Level] <TraceLevel> [-TraceVerboseObjects] [-Path <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Start-VMTrace** cmdlet starts tracing to a file.
You can use this information for advanced debugging.

## EXAMPLES

### Example 1: Start error tracing
```
PS C:\> Start-VMTrace -Level Error
```

This command starts tracing at the level of Error.

## PARAMETERS

### -Level
Specifies the level of tracing.
The acceptable values for this parameter are:

- Off
- Error
- Warning
- Info
- Verbose

```yaml
Type: TraceLevel
Parameter Sets: (All)
Aliases:
Accepted values: Error, Warning, Info, Verbose

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path
Specifies the path of the file where this cmdlet stores the trace information.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TraceVerboseObjects
Specifies that tracing uses verbose objects.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Stop-VMTrace](./Stop-VMTrace.md)

