---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: microsoft.windows.appbackgroundtask.commands.dll-Help.xml
Module Name: AppBackgroundTask
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/appbackgroundtask/enable-appbackgroundtaskdiagnosticlog?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-AppBackgroundTaskDiagnosticLog
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Disable-AppBackgroundTaskDiagnosticLog](./Disable-AppBackgroundTaskDiagnosticLog.md)

