---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.FailoverClusters.PowerShell.dll-Help.xml
Module Name: FailoverClusters
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/failoverclusters/move-clustergroup?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Move-ClusterGroup
---

# Move-ClusterGroup

## SYNOPSIS
Moves a clustered role (a resource group) from one node to another in a failover cluster.

## SYNTAX

```
Move-ClusterGroup [[-Name] <String>] [[-Node] <String>] [-IgnoreLocked] [-Wait <Int32>]
 [-InputObject <PSObject>] [-Cluster <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Move-ClusterGroup** cmdlet moves a clustered role (a resource group) from one node to another in a failover cluster.

Moving a resource group is a way of simulating failover.
Running this cmdlet is also an appropriate step to take in preparation for routine maintenance on a node.

## EXAMPLES

### Example 1
```
PS C:\> Move-ClusterGroup -Name MyFileServer
Name                       OwnerNode                                      State 
----                       ---------                                      ----- 
MyFileServer               node1                                         Online
```

This example moves the clustered service called MyFileServer from the current owner node to any other node.

### Example 2
```
PS C:\> Move-ClusterGroup -Name MyFileServer -Node node2
Name                       OwnerNode                                      State 
----                       ---------                                      ----- 
MyFileServer               node2                                         Online
```

This example moves the resource group called MyFileServer from the current owner node to the node named node2.

### Example 3
```
PS C:\> Get-ClusterNode node3 | Get-ClusterGroup | Move-ClusterGroup
Name                       OwnerNode                                      State 
----                       ---------                                      ----- 
Available Storage          node4                                         Online 
Cluster Group              node1                                         Online 
MyFileServer               node1                                         Online
```

This example moves all resource groups that are currently owned by the node named node3 to other nodes.
Use this cmdlet before performing maintenance on the specified node.

### Example 4
```
PS C:\> Move-ClusterGroup -Name MyFileServer -Node node2 -Wait 0
Name                       OwnerNode                                      State 
----                       ---------                                      ----- 
MyFileServer              node2                                        Pending
```

This example moves the resource group called MyFileServer from the current owner node to the node named `node2`.
Information about MyFileServer is displayed immediately, while it is in the process of being moved.

## PARAMETERS

### -Cluster
Specifies the name of the cluster on which to run this cmdlet.
If the input for this parameter is `.` or it is omitted, then the cmdlet runs on the local cluster.

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

### -IgnoreLocked
Specifies that locked groups are ignored when running the cmdlet.

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
Specifies the resource group to move.

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
Specifies the name of the resource group to move.

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
Specifies the name of the cluster node to which to move the resource group.

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
Specifies the time in seconds to wait for the cmdlet.
If the **Wait** parameter is not specified, then the cmdlet waits for completion.
If `-Wait 0` is specified, then the call is initiated and the cmdlet returns without waiting.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.FailoverClusters.PowerShell.ClusterGroup

## OUTPUTS

### Microsoft.FailoverClusters.PowerShell.ClusterGroup

## NOTES

## RELATED LINKS

[Add-ClusterGroup](./Add-ClusterGroup.md)

[Get-ClusterGroup](./Get-ClusterGroup.md)

[Remove-ClusterGroup](./Remove-ClusterGroup.md)

[Start-ClusterGroup](./Start-ClusterGroup.md)

[Stop-ClusterGroup](./Stop-ClusterGroup.md)

