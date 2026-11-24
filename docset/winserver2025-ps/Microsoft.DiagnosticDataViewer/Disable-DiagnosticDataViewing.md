---
external help file: DDVCmdlets.dll-Help.xml
Module Name: Microsoft.DiagnosticDataViewer
online version: https://learn.microsoft.com/powershell/module/microsoft.diagnosticdataviewer/disable-diagnosticdataviewing?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-DiagnosticDataViewing
---

# Disable-DiagnosticDataViewing

## SYNOPSIS
Disables diagnostic data viewing.

## SYNTAX

```
Disable-DiagnosticDataViewing [<CommonParameters>]
```

## DESCRIPTION
This cmdlet disables diagnostic data viewing.
Once diagnostic data viewing is disabled, this tool will throw an error.
Note that disabling diagnostic data viewing will also delete the available history of diagnostic data on the device.

## EXAMPLES

### EXAMPLE 1
```
Disable-DiagnosticDataViewing
```

Disable Diagnostic Data Viewing.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### System.String

## NOTES
Requires Windows 10 version 17134 (1803) or higher

## RELATED LINKS

