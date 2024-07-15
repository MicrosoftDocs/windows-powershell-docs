---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.FailoverClusters.PowerShell.dll-Help.xml
Module Name: FailoverClusters
ms.date: 11/22/2022
online version: https://learn.microsoft.com/powershell/module/failoverclusters/get-clustersharedvolumestate?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ClusterSharedVolumeState
---

# Get-ClusterSharedVolumeState

## SYNOPSIS
Gets the state of Cluster Shared Volumes in a cluster.

## SYNTAX

```
Get-ClusterSharedVolumeState [-Node <StringCollection>] [[-Name] <StringCollection>]
 [-InputObject <PSObject>] [-Cluster <String>] [<CommonParameters>]
```

## DESCRIPTION

The `Get-ClusterSharedVolumeState` cmdlet gets the state of Cluster Shared Volumes in a cluster.

## EXAMPLES

### Example 1

```powershell
Get-ClusterSharedVolumeState
```

This command gets the state of Cluster Shared Volumes on the local cluster.

## PARAMETERS

### -Cluster

Specifies the name of the cluster on which to run this cmdlet. If you specify a period (`.`) or
don't specify this parameter, the cmdlet runs on the local cluster.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

Specifies the input to this cmdlet. You can use this parameter, or you can pipe the input to this
cmdlet.

```yaml
Type: PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name

Specifies the names, as a collection of strings, of the Cluster Shared Volumes for which to get
state information.

```yaml
Type: StringCollection
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Node

Specifies the names, as a collection of strings, of the cluster nodes for which to get the state of
Cluster Shared Volumes.

```yaml
Type: StringCollection
Parameter Sets: (All)
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
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.FailoverClusters.PowerShell.Cluster, Microsoft.FailoverClusters.PowerShell.ClusterNode, Microsoft.FailoverClusters.PowerShell.ClusterSharedVolume

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-ClusterSharedVolume](./Get-ClusterSharedVolume.md)
