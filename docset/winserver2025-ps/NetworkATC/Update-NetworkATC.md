---
external help file: NetworkAtc-help.xml
Module Name: NetworkATC
ms.date: 03/14/2025
online version: https://learn.microsoft.com/powershell/module/networkatc/update-networkatc?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Update-NetworkATC
---

# Update-NetworkATC

## SYNOPSIS
Updates the Network ATC configuration settings.

## SYNTAX

```
Update-NetworkATC [[-DriftTimerInMinutes] <Int32>] [[-ConfigurationChangeInSeconds] <Int32>]
 [<CommonParameters>]
```

## DESCRIPTION

The `Update-NetworkATC` cmdlet updates the global configuration settings for Network ATC, such as
the drift detection timer and the configuration change detection interval.

## EXAMPLES

### Example 1

```powershell
Update-NetworkATC -DriftTimerInMinutes 10 -ConfigurationChangeInSeconds 30
```

This example updates the Network ATC configuration to set the drift detection timer to `10` minutes
and the configuration change detection interval to `30` seconds.

## PARAMETERS

### -ConfigurationChangeInSeconds

Specifies the interval, in seconds, for detecting changes in network configuration.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DriftTimerInMinutes

Specifies the timer, in minutes, for detecting drift in network configuration settings.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Update-NetIntentAdapter](Update-NetIntentAdapter.md)

[Update-NetIntentType](Update-NetIntentType.md)
