---
external help file: microsoft.windows.appbackgroundtask.commands.dll-Help.xml
Module Name: AppBackgroundTask
ms.date: 10/29/2017
online version: https://learn.microsoft.com/powershell/module/appbackgroundtask/disable-appbackgroundtaskdiagnosticlog?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-AppBackgroundTaskDiagnosticLog
---

# Disable-AppBackgroundTaskDiagnosticLog

## SYNOPSIS
Disables background task logging in Event Viewer.

## SYNTAX

```
Disable-AppBackgroundTaskDiagnosticLog [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Disable-AppBackgroundTaskDiagnosticLog** cmdlet disables background task logging in Event Viewer.
You must have administrator access to disable background task logging.

## EXAMPLES

### Example 1: Disable background task logging
```
PS C:\> Disable-AppBackgroundTaskDiagnosticLog
```

This command turns off background task logging in Event Viewer.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Enable-AppBackgroundTaskDiagnosticLog](./Enable-AppBackgroundTaskDiagnosticLog.md)

