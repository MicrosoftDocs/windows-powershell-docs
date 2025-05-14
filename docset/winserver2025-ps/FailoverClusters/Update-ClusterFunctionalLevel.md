---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.FailoverClusters.PowerShell.dll-Help.xml
Module Name: FailoverClusters
ms.date: 11/23/2022
online version: https://learn.microsoft.com/powershell/module/failoverclusters/update-clusterfunctionallevel?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Update-ClusterFunctionalLevel
---

# Update-ClusterFunctionalLevel

## SYNOPSIS
Updates the functional level of a mixed-version cluster.

## SYNTAX

```
Update-ClusterFunctionalLevel [-Force] [-WhatIf] [-InputObject <PSObject>] [-Cluster <String>]
 [<CommonParameters>]
```

## DESCRIPTION

The `Update-ClusterFunctionalLevel` cmdlet updates the functional level of a mixed-version
cluster. You can update the cluster after all nodes have been updated.

Starting with Windows Server 2016, you can add a node that runs a more recent version of the Windows
operating system into a cluster of nodes that run a previous version of the Windows operating
system. To add a cluster node, use the `Add-ClusterNode` cmdlet.

After you add a node that runs a different version of the Windows operating system, the cluster
becomes a mixed-version cluster. You can implement a mixed-version cluster to continue to run while
you upgrade the operating system on each node in the cluster.

We recommend that you upgrade all nodes in the cluster within a month. We don't recommend using a
mixed-version cluster permanently.

You can use this cmdlet to support a rolling operating system upgrade for a cluster. If you use
cluster that runs Hyper-V in which all the nodes run Windows Server 2012 R2, you can upgrade the
nodes of that cluster without downtime for your virtual machines.

First, drain one cluster node by specifying the **Drain** parameter of the `Suspend-ClusterNode`
cmdlet. This cmdlet causes all virtual machines to live-migrate to one of the other hosts.

Next, remove the host from the cluster by using the `Remove-ClusterNode` cmdlet.

Next, install a new version of the operating system. Don't perform an upgrade or in-place
installation.

Next, add the Hyper-V role and the **Failover Clustering** feature by using the
`Install-WindowsFeature` cmdlet. For more information, type `Get-Help Install-WindowsFeature`.

Finally, add the node into the cluster by using the `Add-ClusterNode` cmdlet.

Repeat these steps for each node of the cluster.

## EXAMPLES

### Example 1: Test a possible update

```powershell
Update-ClusterFunctionalLevel -WhatIf
```

This command tests whether an update would finish successfully. Because the command includes the
**WhatIf** common parameter, the command doesn't perform the update.

### Example 2: Update a cluster functional level

```powershell
Update-ClusterFunctionalLevel -Cluster "cluster_17"
```

This command updates the cluster functional level of the cluster named `cluster_17`. All of the
nodes of this cluster must already be updated before you run this command.

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

### -Force

Forces the command to run without asking for user confirmation.

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

### -WhatIf

Shows what would happen if the cmdlet runs. The cmdlet isn't run.

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

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.FailoverClusters.PowerShell.Cluster

This cmdlet accepts a **Cluster**. This cmdlet updates the functional level of this cluster.

## OUTPUTS

### Microsoft.FailoverClusters.PowerShell.Cluster

This cmdlet returns a **Cluster**. This cmdlet updates the functional level of this cluster.

## NOTES

* This cmdlet performs a one-time, one-way transformation of the cluster functional level. You
  cannot lower this level.

## RELATED LINKS

[Add-ClusterNode](./Add-ClusterNode.md)

[Suspend-ClusterNode](./Suspend-ClusterNode.md)

[Remove-ClusterNode](./Remove-ClusterNode.md)
