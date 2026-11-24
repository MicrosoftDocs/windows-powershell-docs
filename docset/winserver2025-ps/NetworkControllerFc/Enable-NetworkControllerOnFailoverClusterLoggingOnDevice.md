---
external help file: LoggingFc.psm1-help.xml
Module Name: NetworkControllerFc
ms.date: 02/21/2024
online version: https://learn.microsoft.com/powershell/module/networkcontrollerfc/enable-networkcontrolleronfailoverclusterloggingondevice?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-NetworkControllerOnFailoverClusterLoggingOnDevice
---

# Enable-NetworkControllerOnFailoverClusterLoggingOnDevice

## SYNOPSIS

## SYNTAX

```
Enable-NetworkControllerOnFailoverClusterLoggingOnDevice [-DeviceName] <String> [-Device] <String>
 [<CommonParameters>]
```

## DESCRIPTION

Creates logman trace session, starts logman trace, and creates a scheduled task to periodically call
SdnDiagnosticTask.exe.

## EXAMPLES

### Example 1

```powershell
PS C:\> {{ Add example code here }}
```

{{ Add example description here }}

## PARAMETERS

### -Device

Valid values: Server, Gateway, or Mux.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DeviceName

DeviceName necessary to create remote session.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS
