---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Dtc.PowerShell.dll-Help.xml
Module Name: MsDtc
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/msdtc/start-dtcdiagnosticresourcemanager?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Start-DtcDiagnosticResourceManager
---

# Start-DtcDiagnosticResourceManager

## SYNOPSIS
Starts a diagnostic Resource Manager.

## SYNTAX

```
Start-DtcDiagnosticResourceManager [[-Port] <Int32>] [[-Name] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Start-DtcDiagnosticResourceManager** cmdlet starts a diagnostic Resource Manager (RM) as a Windows PowerShell® background job.

## EXAMPLES

### Example 1: Start a diagnostic resource manager
```
PS C:\> Start-DtcDiagnosticResourceManager -Port 17124 -Name "testRM"
```

This example starts a DTC diagnostic resource manager.

## PARAMETERS

### -Name
Specifies the name for the diagnostic resource manager to start.
You can later refer to the RM by using this name.
If you do not specify a name, the RM instance ID, a GUID, is always assigned to the RM and you can refer to it by that ID.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Port
Specifies the listening port of the test RM.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Join-DtcDiagnosticResourceManager](./Join-DtcDiagnosticResourceManager.md)

[Stop-DtcDiagnosticResourceManager](./Stop-DtcDiagnosticResourceManager.md)

