---
external help file: DDVCmdlets.dll-Help.xml
Module Name: Microsoft.DiagnosticDataViewer
online version: https://learn.microsoft.com/powershell/module/microsoft.diagnosticdataviewer/get-diagnosticdatatypes?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-DiagnosticDataTypes
---

# Get-DiagnosticDataTypes

## SYNOPSIS
Fetches the mapping of diagnostic data type identifiers to their corresponding descriptions.

## SYNTAX

```
Get-DiagnosticDataTypes [<CommonParameters>]
```

## DESCRIPTION
This cmdlet shows the mapping between diagnostic data type identifiers to their official descriptions.
Each diagnostic data event is grouped into a Data Type based on how Microsoft uses the data.
It may take some time for descriptions to be loaded.

## EXAMPLES

### EXAMPLE 1
```
Get-DiagnosticDataTypes
```

Fetches Windows Diagnostic Data diagnostic data types.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### DDVCmdlets.Containers.DiagnosticDataType
Diagnostic data type information.

## NOTES
Requires Windows 10 version 17134 (1803) or higher

## RELATED LINKS

[About Windows Diagnostic Data](/windows/privacy/windows-diagnostic-data)
