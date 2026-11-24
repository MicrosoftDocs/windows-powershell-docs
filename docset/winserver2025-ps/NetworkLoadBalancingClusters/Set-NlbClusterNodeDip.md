---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.NetworkLoadBalancingClusters.PowerShell.dll-Help.xml
Module Name: NetworkLoadBalancingClusters
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/networkloadbalancingclusters/set-nlbclusternodedip?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-NlbClusterNodeDip
---

# Set-NlbClusterNodeDip

## SYNOPSIS
Edits the dedicated IP address of a NLB cluster.

## SYNTAX

### NonPipeline (Default)
```
Set-NlbClusterNodeDip [-HostName <String>] -InterfaceName <String> [-IP] <IPAddress> -NewDip <IPAddress>
 [<CommonParameters>]
```

### Pipeline
```
Set-NlbClusterNodeDip -InputObject <ClusterNodeDip[]> -NewDip <IPAddress> [<CommonParameters>]
```

## DESCRIPTION
The **Set-NlbClusterNodeDIP** cmdlet edits the dedicated IP address of a Network Load Balancing (NLB) cluster.
This cmdlet can be used to edit the IP address and subnet mask for the dedicated IP address.

This operation changes the configuration on all cluster nodes.
As a result, the NLB cluster will have to restart the convergence process on all nodes to guarantee that configuration changes have been applied on all nodes and that a consistent state is reached.
Any additional operations on the NLB cluster should not be initiated until all cluster nodes have completed the convergence process and are back to the converged state.

ps_nlbc_checkstate_remark

## EXAMPLES

### Example 1: Change a cluster virtual IP
```
PS C:\>Get-NlbClusterNodeDip -IP fe80::a585:202d:f7f6:2636 | Set-NlbClusterNodeDip -NewDip fe80::a9cb:eafb:e841:d8cf
Node                       IPAddress                  SubnetMask
----                       ---------                  ----------
node2                      fe80::a9cb:eafb:e841:d8cf
```

This command changes the cluster virtual IP from fe80::a585:202d:f7f6:2636 to fe80::a9cb:eafb:e841:d8cf.

## PARAMETERS

### -HostName
Specifies the name of the cluster host against which this cmdlet is run.
If this parameter is omitted or a value of `.` is entered, then the local cluster is assumed.

```yaml
Type: String
Parameter Sets: NonPipeline
Aliases: Host, HN, H

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IP
Specifies the IP address for the cluster node on which this cmdlet sets the dedicated IP.

```yaml
Type: IPAddress
Parameter Sets: NonPipeline
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Specifies an array of nodes of the cluster to which this cmdlet sets the dedicated IP.

```yaml
Type: ClusterNodeDip[]
Parameter Sets: Pipeline
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -InterfaceName
Specifies the interface to which NLB is bound.
This is the interface of the cluster against which this cmdlet is run.

```yaml
Type: String
Parameter Sets: NonPipeline
Aliases: Interface, IN, I

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.NetworkLoadBalancingClusters.PowerShell.ClusterNodeDip

## OUTPUTS

### Microsoft.NetworkLoadBalancingClusters.PowerShell.ClusterNodeDip

## NOTES

## RELATED LINKS

[Add-NlbClusterNodeDip](./Add-NlbClusterNodeDip.md)

[Get-NlbClusterNodeDip](./Get-NlbClusterNodeDip.md)

[Remove-NlbClusterNodeDip](./Remove-NlbClusterNodeDip.md)

