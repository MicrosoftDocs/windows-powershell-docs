---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.FailoverClusters.PowerShell.dll-Help.xml
Module Name: FailoverClusters
ms.date: 10/21/2022
online version: https://learn.microsoft.com/powershell/module/failoverclusters/set-clusterparameter?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-ClusterParameter
---

# Set-ClusterParameter

## SYNOPSIS
Controls specific properties of an object in a failover cluster, such as a resource, a group, or a
network.

## SYNTAX

### NoMultiple (Default)

```
Set-ClusterParameter [-InputObject <PSObject>] [-Create] [-Delete] [-Cluster <String>]
 [<CommonParameters>]
```

### Single Parameter

```
Set-ClusterParameter [-InputObject <PSObject>] [[-Name] <String>] [[-Value] <PSObject>] [-Create]
 [-Delete] [-Cluster <String>] [<CommonParameters>]
```

### Multiple Parameter

```
Set-ClusterParameter [-InputObject <PSObject>] [[-Multiple] <Hashtable>] [-Create] [-Delete]
 [-Cluster <String>] [<CommonParameters>]
```

## DESCRIPTION

The `Set-ClusterParameter` cmdlet controls specific properties of an object in a failover cluster,
such as a resource, a group, or a network.

- For a disk resource, you can set the disk signature or GUID of a disk, and turn maintenance on
  or off for that disk.

- For a Network Name resource, you can set DNS-related information about the resource.

- For an IP address resource, you can set DHCP-related information about the IP Address resource.

- For resources used by virtual machines, you can set details about the settings for the virtual
  machines.

## EXAMPLES

### Example 1

```powershell
Get-ClusterResource -Name "Cluster Disk 3" | Set-ClusterOwnerNode -Owners node1,node2
```

This example sets the possible owners for cluster named `Cluster Disk 3` on the local cluster to the
nodes named `node1` and `node2`.

### Example 2

```powershell
Set-ClusterOwnerNode -Group cluster12FS -Owners node3,node2
```

This example sets the preferred owners for the clustered service named `cluster12FS` to the node
named `node3` followed by the node named `node2` on the local cluster.

## PARAMETERS

### -Cluster

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

### -Create

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Delete

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

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

### -Multiple

```yaml
Type: Hashtable
Parameter Sets: Multiple Parameter
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name

```yaml
Type: String
Parameter Sets: Single Parameter
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Value

```yaml
Type: PSObject
Parameter Sets: Single Parameter
Aliases:

Required: False
Position: 1
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

### Microsoft.FailoverClusters.PowerShell.Cluster

### Microsoft.FailoverClusters.PowerShell.ClusterGroup

### Microsoft.FailoverClusters.PowerShell.ClusterNetwork

### Microsoft.FailoverClusters.PowerShell.ClusterNetworkInterface

### Microsoft.FailoverClusters.PowerShell.ClusterNode

### Microsoft.FailoverClusters.PowerShell.ClusterParameter

### Microsoft.FailoverClusters.PowerShell.ClusterResource

### Microsoft.FailoverClusters.PowerShell.ClusterResourceType

### Microsoft.FailoverClusters.PowerShell.ClusterSharedVolume

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-ClusterParameter](./Get-ClusterParameter.md)
