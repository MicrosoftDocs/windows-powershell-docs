---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-anbarr
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: microsoft.windows.appbackgroundtask.commands.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Enable-AppBackgroundTaskDiagnosticLog
ms.reviewer:
ms.assetid: 02D467DC-414B-41B1-A5DB-7650A2E8B8AC
---

# Enable-AppBackgroundTaskDiagnosticLog

## SYNOPSIS
Enables background task logging in Event Viewer.

## SYNTAX

```
Enable-AppBackgroundTaskDiagnosticLog [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Enable-AppBackgroundTaskDiagnosticLog** cmdlet enables background task logging in Event Viewer.
You must have administrator access to enable background task logging.

## EXAMPLES

### Example 1: Enable background task logging
```
PS C:\> Enable-AppBackgroundTaskDiagnosticLog
```

This command turns on background task logging in Event Viewer.

## PARAMETERS

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Disable-AppBackgroundTaskDiagnosticLog](./Disable-AppBackgroundTaskDiagnosticLog.md)

