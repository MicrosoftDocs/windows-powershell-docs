---
external help file: NetworkAtc-help.xml
Module Name: NetworkATC
ms.date: 03/14/2025
online version: https://learn.microsoft.com/powershell/module/networkatc/get-netintentallgoalstates?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-NetIntentAllGoalStates
---

# Get-NetIntentAllGoalStates

## SYNOPSIS
Looks up all intent goal state configurations available.

## SYNTAX

```
Get-NetIntentAllGoalStates [[-ClusterName] <String>] [[-ComputerName] <String>] [<CommonParameters>]
```

## DESCRIPTION

The `Get-NetIntentAllGoalStates` retrieves the goal states stored for each intent. These
configurations are the settings used for initial provisioning and drift checks. This information is
useful for debugging and troubleshooting.

## EXAMPLES

### EXAMPLE 1

```powershell
Get-NetIntentAllGoalStates -ComputerName "Server01"
```

This example retrieves all of the network intent goal states from the `Server01` standalone host.

## PARAMETERS

### -ClusterName

Specifies the name of the cluster for which the goal states are to be retrieved.

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

### -ComputerName

Specifies the name of the computer for which the goal states are to be retrieved.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
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

## OUTPUTS

## NOTES

## RELATED LINKS
