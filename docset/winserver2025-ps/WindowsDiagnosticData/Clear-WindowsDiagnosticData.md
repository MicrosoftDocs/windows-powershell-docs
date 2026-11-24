---
external help file: ClearWindowsDiagnosticData.psm1-help.xml
Module Name: WindowsDiagnosticData
online version: https://learn.microsoft.com/powershell/module/windowsdiagnosticdata/clear-windowsdiagnosticdata?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Clear-WindowsDiagnosticData
---

# Clear-WindowsDiagnosticData

## SYNOPSIS
Sends a request to delete all uploaded diagnostic data sent to Microsoft from the current device.

## SYNTAX

```
Clear-WindowsDiagnosticData [-Force] [<CommonParameters>]
```

## DESCRIPTION
Sends a request to delete the uploaded diagnostic data sent to Microsoft from the current device.
This cmdlet is only supported on Windows Server 2016 and later.

## EXAMPLES

### EXAMPLE 1
```
Clear-WindowsDiagnosticData
```

### EXAMPLE 2
```
Clear-WindowsDiagnosticData -Force
```

## PARAMETERS

### -Force
The cmdlet will run without asking for confirmation.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.
For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS
