---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.FailoverClusters.PowerShell.dll-Help.xml
Module Name: FailoverClusters
ms.date: 11/22/2022
online version: https://learn.microsoft.com/powershell/module/failoverclusters/move-clustersharedvolume?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Move-ClusterSharedVolume
---

# Move-ClusterSharedVolume

## SYNOPSIS
Moves a Cluster Shared Volume (CSV) to ownership by a different node in a failover cluster.

## SYNTAX

```
Move-ClusterSharedVolume [[-Name] <String>] [[-Node] <String>] [-Wait <Int32>]
 [-InputObject <PSObject>] [-Cluster <String>] [<CommonParameters>]
```

## DESCRIPTION

The `Move-ClusterSharedVolume` cmdlet moves a Cluster Shared Volume (CSV) to ownership by a
different node in a failover cluster.

On a failover cluster that uses CSVs, at any given time, access to each CSV is controlled by a
particular node, called the owner of that CSV. However, a single CSV can contain virtual hard disk
(VHD) files used by multiple clustered virtual machines that are distributed across multiple cluster
nodes.

## EXAMPLES

### Example 1

```powershell
Move-ClusterSharedVolume -Name "Cluster Disk 3"
```

This example moves the Cluster Shared Volume called `Cluster Disk 3` to another cluster node.

### Example 2

```powershell
Move-ClusterSharedVolume -Name "Cluster Disk 3" -Node node1
```

This example moves the Cluster Shared Volume called `Cluster Disk 3` to the node named `node1`.

## PARAMETERS

### -Cluster

Specifies the name of the cluster on which to run this cmdlet. If the input for this parameter is
`.` or it is omitted, then the cmdlet runs on the local cluster.

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

Specifies the Cluster Shared Volume to move.

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

Specifies the name of the Cluster Shared Volume to move.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Node

Specifies the name of the cluster node to which to move the Cluster Shared Volume.

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

### -Wait

Specifies the time in seconds to wait for the cmdlet. If the **Wait** parameter isn't specified,
then the cmdlet waits for completion. If `-Wait 0` is specified, then the call is initiated and the
cmdlet returns without waiting.

```yaml
Type: Int32
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

### Microsoft.FailoverClusters.PowerShell.ClusterSharedVolume

## OUTPUTS

### Microsoft.FailoverClusters.PowerShell.ClusterSharedVolume

## NOTES

## RELATED LINKS

[Add-ClusterSharedVolume](./Add-ClusterSharedVolume.md)

[Get-ClusterSharedVolume](./Get-ClusterSharedVolume.md)

[Remove-ClusterSharedVolume](./Remove-ClusterSharedVolume.md)

[Resume-ClusterResource](./Resume-ClusterResource.md)

[Start-ClusterResource](./Start-ClusterResource.md)

[Stop-ClusterResource](./Stop-ClusterResource.md)

[Suspend-ClusterResource](./Suspend-ClusterResource.md)
