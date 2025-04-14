---
external help file: DDVCmdlets.dll-Help.xml
Module Name: Microsoft.DiagnosticDataViewer
online version: https://learn.microsoft.com/powershell/module/microsoft.diagnosticdataviewer/enable-diagnosticdataviewing?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-DiagnosticDataViewing
---

# Enable-DiagnosticDataViewing

## SYNOPSIS
Enables diagnostic data viewing.

## SYNTAX

```
Enable-DiagnosticDataViewing [<CommonParameters>]
```

## DESCRIPTION
This cmdlet enables diagnostic data viewing.
Once enabled, the device henceforth will start recording each diagnostic data event uploaded to Microsoft, where the total history is limited by the diagnostic store capacity.
It may take some time for events to be shown.

## EXAMPLES

### EXAMPLE 1
```
Enable-DiagnosticDataViewing
```

Enable Diagnostic Data Viewing.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### System.String
## NOTES
Requires Windows 10 version 17134 (1803) or higher

## RELATED LINKS
