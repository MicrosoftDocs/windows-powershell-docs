---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: BootEventCollector-help.xml
Module Name: BootEventCollector
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/booteventcollector/save-sbeclogsession?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Save-SbecLogSession
---

# Save-SbecLogSession

## SYNOPSIS
Flushes the buffers in a log session to disk.

## SYNTAX

### Object
```
Save-SbecLogSession -Session <TraceSessionInfo[]> [<CommonParameters>]
```

### Name
```
Save-SbecLogSession -Name <String[]> [<CommonParameters>]
```

## DESCRIPTION
The **Save-SbecLogSession** cmdlet flushes the buffers in a log session to disk.
The session may be identified either by name or as an object.

## EXAMPLES


## PARAMETERS

### -Name
Specifies an array of session names.

```yaml
Type: String[]
Parameter Sets: Name
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Session
Specifies an array of **SbecEtwTrace.TraceSessionInfo** objects.

```yaml
Type: TraceSessionInfo[]
Parameter Sets: Object
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### SbecEtwTrace.TraceSessionInfo
This cmdlet accepts **SbecEtwTrace.TraceSessionInfo** objects as the sessions to flush the buffers on.

## OUTPUTS

### None.

## NOTES

## RELATED LINKS

[Get-SbecLogSession](./Get-SbecLogSession.md)

[Set-SbecLogSession](./Set-SbecLogSession.md)

[Start-SbecLogSession](./Start-SbecLogSession.md)

[Start-SbecSimpleLogSession](./Start-SbecSimpleLogSession.md)

[Start-SbecNtKernelLogSession](./Start-SbecNtKernelLogSession.md)

[Stop-SbecLogSession](./Stop-SbecLogSession.md)

