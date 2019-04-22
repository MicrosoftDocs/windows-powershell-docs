---
external help file: NLB_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: kenwith
author: kenwith
ms.assetid: DCA02082-993D-45C4-88FF-82319C552C8A
manager: dansimp
---

# Start-NlbClusterNode

## SYNOPSIS
Starts a Network Load Balancing (NLB) cluster node.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Start-NlbClusterNode [[-HostName] <String>] [-InterfaceName <String>]
```

### UNNAMED_PARAMETER_SET_2
```
Start-NlbClusterNode -InputObject <Node>
```

## DESCRIPTION
The **Start-NlbClusterNode** cmdlet starts a node in a Network Load Balancing (NLB) cluster.
Once the node is started, NLB will include that node in load balancing network traffic.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Start-NlbClusterNode -InputObject node2
Name                State               Interface           HostID 
----                -----               ---------           ------ 
node2               Converged           vlan-3              2
```

This example starts cluster node named node2 on the local cluster.

## PARAMETERS

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
Specifies the cluster node to start.

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

[Stop-NlbClusterNode](./Stop-NlbClusterNode.md)

[Suspend-NlbClusterNode](./Suspend-NlbClusterNode.md)

