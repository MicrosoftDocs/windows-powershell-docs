---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-anbarr
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: BootEventCollector-help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-SbecLogSession
ms.reviewer:
ms.assetid: 4E692779-BD6B-44E2-8ED3-FE0806827755
---

# Get-SbecLogSession

## SYNOPSIS
Gets the running log sessions.

## SYNTAX

```
Get-SbecLogSession [[-Name] <String>] [-KdOnly] [[-SimulateError] <Int32>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SbecLogSession** cmdlet gets the ETW log sessions that are currently running.
This operation does not get log sessions defined in the registry for AutoLogger.

This cmdlet returns the **SbecEtwTrace.TraceSessionInfo** objects, whose properties contain most of the interesting information.
More details are available in the Trace property.

## EXAMPLES


## PARAMETERS

### -KdOnly
Indicates that this operation gets only log sessions that are configured to forward events through the kernel transport to the collector.

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

### -Name
Specifies the name of a log session.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SimulateError
Simulate a Windows error, and cause the function to throw.
You can specify this parameter to test error handling.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None.

## OUTPUTS

### SbecEtwTrace.TraceSessionInfo
The **SbecEtwTrace.TraceSessionInfo** class is defined in $PsHome\Modules\BootEventCollector\SbecTraceHelpers.psm1.

## NOTES

## RELATED LINKS

[Save-SbecLogSession](./Save-SbecLogSession.md)

[Set-SbecLogSession](./Set-SbecLogSession.md)

[Start-SbecLogSession](./Start-SbecLogSession.md)

[Start-SbecNtKernelLogSession](./Start-SbecNtKernelLogSession.md)

[Start-SbecSimpleLogSession](./Start-SbecSimpleLogSession.md)

[Stop-SbecLogSession](./Stop-SbecLogSession.md)

