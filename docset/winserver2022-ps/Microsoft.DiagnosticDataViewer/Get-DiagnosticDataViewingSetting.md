---
external help file: DDVCmdlets.dll-Help.xml
Module Name: Microsoft.DiagnosticDataViewer
online version:
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
title: Get-DiagnosticDataViewingSetting
---

# Get-DiagnosticDataViewingSetting

## SYNOPSIS
Fetches whether diagnostic data viewing is currently enabled or disabled.

## SYNTAX

```
Get-DiagnosticDataViewingSetting [<CommonParameters>]
```

## DESCRIPTION
This cmdlet returns the current state of diagnostic data viewing.
This state indicates whether diagnostic data viewing is enabled for this device.
If disabled, this tool will throw an error.

## EXAMPLES

### EXAMPLE 1
```
Get-DiagnosticDataViewingSetting
```

Checks if Diagnostic Data Viewing is enabled.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### System.String
## NOTES
Requires Windows 10 version 17134 (1803) or higher
## RELATED LINKS
