---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Windows.HostGuardianService.Diagnostics.Payload.dll-Help.xml
Module Name: HgsDiagnostics
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hgsdiagnostics/test-hgstracetarget?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Test-HgsTraceTarget
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
You can pipe a target object created by the **New-HgsTraceTarget** cmdlet.

## OUTPUTS

### System.Boolean
This cmdlet returns true if a connection can be opened and the requisite conditions are met by that target; false otherwise.
The cmdlet reports a detailed error if the test fails.

## NOTES

## RELATED LINKS

[New-HgsTraceTarget](./New-HgsTraceTarget.md)

