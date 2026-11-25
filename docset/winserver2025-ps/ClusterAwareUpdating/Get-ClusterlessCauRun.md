---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: ClusterAwareUpdating.dll-Help.xml
Module Name: ClusterAwareUpdating
ms.date: 07/01/2024
online version: https://learn.microsoft.com/powershell/module/clusterawareupdating/get-clusterlesscaurun?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ClusterlessCauRun
---

# Get-ClusterlessCauRun

## SYNOPSIS
Retrieves information about a Cluster-Aware Updating (CAU) run not associated with a cluster.

## SYNTAX

### DefaultParamSet (Default)

```
Get-ClusterlessCauRun [-Credential <PSCredential>] [<CommonParameters>]
```

### ShowClusterNodeState

```
Get-ClusterlessCauRun [-Credential <PSCredential>] [-ShowClusterNodeState] [<CommonParameters>]
```

## DESCRIPTION

The `Get-ClusterlessCauRun` cmdlet retrieves information about a Cluster-Aware Updating (CAU) run
that is not associated with a cluster.

## EXAMPLES

### Example 1

```powershell
Get-ClusterlessCauRun
```

This example displays information about the current CAU run, including the status of each node that
is being updated.

## PARAMETERS

### -Credential

Specifies the administrative credentials for the target cluster.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ShowClusterNodeState

Displays detailed information about the state of each node in the CAU run.

```yaml
Type: SwitchParameter
Parameter Sets: ShowClusterNodeState
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](/powershell/module/microsoft.powershell.core/about/about_commonparameters).

## INPUTS

### None

## OUTPUTS

### Microsoft.ClusterAwareUpdating.CauWmiObject

### Microsoft.ClusterAwareUpdating.ClusterlessCauRun

### Microsoft.ClusterAwareUpdating.RunState

## NOTES

## RELATED LINKS

[Invoke-ClusterlessCauRun](invoke-clusterlesscaurun.md)
