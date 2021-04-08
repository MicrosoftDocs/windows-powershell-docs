---
author: Kateyanne
external help file: NLB_Cmdlets.xml
manager: dansimp
Module Name: NetworkLoadBalancingClusters
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/networkloadbalancingclusters/set-nlbclusternodedip?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-NlbClusterNodeDip

## SYNOPSIS
Edits the dedicated IP address of a Network Load Balancing (NLB) cluster.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Set-NlbClusterNodeDip [-IP] <IPAddress> [-HostName <String>] -InterfaceName <String> -NewDip <IPAddress>
```

### UNNAMED_PARAMETER_SET_2
```
Set-NlbClusterNodeDip -InputObject <ClusterNodeDip> -NewDip <IPAddress>
```

## DESCRIPTION
The **Set-NlbClusterNodeDIP** cmdlet edits the dedicated IP address of a Network Load Balancing (NLB) cluster.
This cmdlet can be used to edit the IP address and subnet mask for the dedicated IP address.

This operation changes the configuration on all cluster nodes.
As a result, the NLB cluster will have to restart the convergence process on all nodes to guarantee that configuration changes have been applied on all nodes and that a consistent state is reached.
Any additional operations on the NLB cluster should not be initiated until all cluster nodes have completed the convergence process and are back to the converged state.

ps_nlbc_checkstate_remark

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-NlbClusterNodeDip -IP fe80::a585:202d:f7f6:2636 | Set-NlbClusterNodeDip -NewDip fe80::a9cb:eafb:e841:d8cf
Node                       IPAddress                  SubnetMask 
----                       ---------                  ---------- 
node2                      fe80::a9cb:eafb:e841:d8cf
```

This example changes the cluster virtual IP from fe80::a585:202d:f7f6:2636 to fe80::a9cb:eafb:e841:d8cf.

## PARAMETERS

### -HostName
Specifies the name of the cluster host against which this cmdlet is run.
If this parameter is omitted or a value of `.` is entered, then the local cluster is assumed.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: hn

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IP
Specifies the IP address for the cluster node on which the dedicated IP will be set.

```yaml
Type: IPAddress
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Specifies the node of the cluster to which the dedicated IP address is set.

```yaml
Type: ClusterNodeDip
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

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NewDip
Specifies the new dedicated IP address for the cluster node.

```yaml
Type: IPAddress
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

### Microsoft.NetworkLoadBalancingClusters.PowerShell.ClusterNodeDip

## OUTPUTS

### Microsoft.NetworkLoadBalancingClusters.PowerShell.ClusterNodeDip

## NOTES

## RELATED LINKS

[Add-NlbClusterNodeDip](./Add-NlbClusterNodeDip.md)

[Get-NlbClusterNodeDip](./Get-NlbClusterNodeDip.md)

[Remove-NlbClusterNodeDip](./Remove-NlbClusterNodeDip.md)

