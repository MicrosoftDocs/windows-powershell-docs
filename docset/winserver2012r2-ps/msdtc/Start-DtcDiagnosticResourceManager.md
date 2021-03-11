---
external help file: Microsoft.Dtc.PowerShell.dll-Help.xml
Module Name: MsDtc
online version: 
schema: 2.0.0
title: Start-DtcDiagnosticResourceManager
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/29/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 4EA71110-A579-4C1F-A91B-F24FB99B8BBD
ms.author: v-kaunu
ms.reviewer: brianlic
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
PS C:\>Start-DtcDiagnosticResourceManager -Port 17124 -Name "testRM"
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Join-DtcDiagnosticResourceManager](./Join-DtcDiagnosticResourceManager.md)

[Stop-DtcDiagnosticResourceManager](./Stop-DtcDiagnosticResourceManager.md)

