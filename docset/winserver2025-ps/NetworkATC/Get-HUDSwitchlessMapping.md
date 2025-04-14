---
external help file: NetworkAtc-help.xml
Module Name: NetworkATC
ms.date: 03/14/2025
online version: https://learn.microsoft.com/powershell/module/networkatc/get-hudswitchlessmapping?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-HUDSwitchlessMapping
---

# Get-HUDSwitchlessMapping

## SYNOPSIS
Retrieves the HUD switchless mapping configuration for the specified cluster.

## SYNTAX

```
Get-HUDSwitchlessMapping [-ClusterName] <String> [<CommonParameters>]
```

## DESCRIPTION

The `Get-HUDSwitchlessMapping` cmdlet queries retrieves the configuration mapping for switchless
operation within the HUD subsystem on the target cluster.

## EXAMPLES

### Example 1

```powershell
Get-HUDSwitchlessMapping -ClusterName "Cluster01"
```

This example retrieves the HUD switchless mapping configuration for the cluster `Cluster01`.

## PARAMETERS

### -ClusterName

Specifies the name of the cluster.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
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
