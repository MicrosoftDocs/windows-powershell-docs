---
author: brianlic-msft
description: 
external help file: BootEventCollector-help.xml
keywords: powershell, cmdlet
manager: alanth
ms.date: 2016-12-20
ms.prod: powershell
ms.technology: powershell
ms.topic: reference
online version: 
schema: 2.0.0
title: Stop-SbecLogSession
ms.assetid: 94CAD99C-49C6-4728-8706-E04C0B34B8A0
---

# Stop-SbecLogSession

## SYNOPSIS
Stops a log session.

## SYNTAX

### Object
```
Stop-SbecLogSession -Session <TraceSessionInfo[]> [<CommonParameters>]
```

### Name
```
Stop-SbecLogSession -Name <String[]> [<CommonParameters>]
```

## DESCRIPTION
The **Stop-SbecLogSession** cmdlet stops a log session.

## EXAMPLES

### 1:
```

```

## PARAMETERS

### -Name
Specifies the name of the log session to stop.

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
Specifies the session objects to stop.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### SbecEtwTrace.TraceSessionInfo
The **SbecEtwTrace.TraceSessionInfo** class is defined in $PsHome\Modules\BootEventCollector\SbecTraceHelpers.psm1.

## OUTPUTS

### None.

## NOTES

## RELATED LINKS

[Get-SbecLogSession](./Get-SbecLogSession.md)

[Save-SbecLogSession](./Save-SbecLogSession.md)

[Set-SbecLogSession](./Set-SbecLogSession.md)

[Start-SbecLogSession](./Start-SbecLogSession.md)

[Start-SbecNtKernelLogSession](./Start-SbecNtKernelLogSession.md)

[Start-SbecSimpleLogSession](./Start-SbecSimpleLogSession.md)

