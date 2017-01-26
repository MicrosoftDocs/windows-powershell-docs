---
author: brianlic-msft
description: 
external help file: Microsoft.Windows.HostGuardianService.Diagnostics.Payload.dll-Help.xml
keywords: powershell, cmdlet
manager: alanth
ms.date: 2016-12-20
ms.prod: powershell
ms.technology: powershell
ms.topic: reference
online version: 
schema: 2.0.0
title: Test-HgsTraceTarget
ms.assetid: E899FBBD-328B-4607-9584-017AF3108816
---

# Test-HgsTraceTarget

## SYNOPSIS
Verifies that a remote Windows PowerShell® session can be opened to the provided target.

## SYNTAX

```
Test-HgsTraceTarget -Target <InputTarget> [<CommonParameters>]
```

## DESCRIPTION
The **Test-HgsTraceTarget** cmdlet verifies that a remote Windows PowerShell® session can be opened to the specified target and that a compatible version of the diagnostic module is available.

## EXAMPLES

### 1:
```

```

## PARAMETERS

### -Target
Specifies the target object to be tested.

```yaml
Type: InputTarget
Parameter Sets: (All)
Aliases: InputObject

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Windows.HostGuardianService.Diagnostics.Payload.InputTarget
You can pipe a target object created by the New-HgsTraceTarget cmdlet.

## OUTPUTS

### System.Boolean
This cmdlet returns true if a connection can be opened and the requisite conditions are met by that target; false otherwise.
The cmdlet reports a detailed error if the test fails.

## NOTES

## RELATED LINKS

[New-HgsTraceTarget](./New-HgsTraceTarget.md)

