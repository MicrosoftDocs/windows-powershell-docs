---
description: Causes Windows Local Administrator Password Solution (LAPS) to process the currently configured policy.
external help file: lapspsh.dll-Help.xml
Module Name: LAPS
online version: https://learn.microsoft.com/powershell/module/laps/invoke-lapspolicyprocessing?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
Locale: en-US
ms.date: 04/10/2023
title: Invoke-LapsPolicyProcessing
---

# Invoke-LapsPolicyProcessing

## SYNOPSIS
Causes Windows Local Administrator Password Solution (LAPS) to process the currently configured
policy.

## SYNTAX

```
Invoke-LapsPolicyProcessing [<CommonParameters>]
```

## DESCRIPTION

The `Invoke-LapsPolicyProcessing` cmdlet tells LAPS to process the currently configured policy.

The cmdlet doesn't return detailed information about the results of the operation. See
[Use Windows LAPS event logs](https://go.microsoft.com/fwlink/?linkid=2234103) for more information
on querying the resultant event log entries to get specific information on the outcome of the
operation.

## EXAMPLES

### Example 1

```powershell
Invoke-LapsPolicyProcessing
```

This example starts the processing of the configured LAPS policy.

## PARAMETERS

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Windows LAPS Overview](https://go.microsoft.com/fwlink/?linkid=2233901)
