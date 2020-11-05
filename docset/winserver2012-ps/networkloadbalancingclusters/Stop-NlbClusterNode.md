---
external help file: NLB_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: C7659763-21A6-48A8-9A65-86D22E5200C5
manager: dansimp
---

# Stop-NlbClusterNode

## SYNOPSIS
Stops a node in a Network Load Balancing (NLB) cluster.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Stop-NlbClusterNode [[-HostName] <String>] [-Drain] [-InterfaceName <String>] [-Timeout <Nullable>]
```

### UNNAMED_PARAMETER_SET_2
```
Stop-NlbClusterNode [-Drain] [-Timeout <Nullable>] -InputObject <Node>
```

## DESCRIPTION
The **Stop-NlbClusterNode** cmdlet stops a node in a Network Load Balancing (NLB) cluster.
When the nodes are stopped in the cluster, client connections that are already in progress are interrupted.
To avoid interrupting active connections, consider using the **Drain** parameter, which allows the node to continue servicing active connections but disables all new traffic to that node.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Stop-NlbClusterNode node2
Name                State               Interface           HostID 
----                -----               ---------           ------ 
node2               Stopped             vlan-3              2
```

This example stops the cluster node named node2 on the local cluster.

### EXAMPLE 2
```
PS C:\>Stop-NlbClusterNode -Drain -Timeout 10
Name                State               Interface           HostID 
----                -----               ---------           ------ 
node3               Stopped             vlan-3              3
```

This example stops the local cluster node.
Before this cmdlet stops the cluster, this cmdlet drains all existing connections for up to 10 minutes.
During that time, new connections will not be established on this node.
Any remaining connections after the 10 minutes will be forcefully terminated.

## PARAMETERS

### -Drain
Drains existing traffic before stopping the cluster node.
If this parameter is omitted, then the existing traffic will be dropped.

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

### -HostName
Specifies the name of the cluster host against which this cmdlet is run.
If this parameter is omitted or a value of `.` is entered, then the local cluster is assumed.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: hn

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Specifies the cluster node to stop.

```yaml
Type: Node
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue, ByPropertyName)
Accept wildcard characters: False
```

### -InterfaceName
Specifies the interface to which NLB is bound.
This is the interface of the cluster against which this cmdlet is run.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Timeout
Specifies the number of minutes to wait for the drain operation before stopping the cluster node.
After the time expires, the existing connections will be dropped.

```yaml
Type: Nullable
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

### Microsoft.NetworkLoadBalancingClusters.PowerShell.Node

## OUTPUTS

### Microsoft.NetworkLoadBalancingClusters.PowerShell.Node

## NOTES

## RELATED LINKS

[Add-NlbClusterNode](./Add-NlbClusterNode.md)

[Get-NlbClusterNode](./Get-NlbClusterNode.md)

[Remove-NlbClusterNode](./Remove-NlbClusterNode.md)

[Resume-NlbClusterNode](./Resume-NlbClusterNode.md)

[Set-NlbClusterNode](./Set-NlbClusterNode.md)

[Start-NlbClusterNode](./Start-NlbClusterNode.md)

[Suspend-NlbClusterNode](./Suspend-NlbClusterNode.md)

