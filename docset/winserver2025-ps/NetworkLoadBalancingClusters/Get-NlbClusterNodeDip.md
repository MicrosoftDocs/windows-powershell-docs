---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.NetworkLoadBalancingClusters.PowerShell.dll-Help.xml
Module Name: NetworkLoadBalancingClusters
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/networkloadbalancingclusters/get-nlbclusternodedip?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-NlbClusterNodeDip
---

# Get-NlbClusterNodeDip

## SYNOPSIS
Gets the dedicated IP address that is queried by the caller.

## SYNTAX

### NonPipeline (Default)
```
Get-NlbClusterNodeDip [-HostName <String>] [-InterfaceName <String>] [-NodeName <String>] [[-IP] <IPAddress>]
 [<CommonParameters>]
```

### Pipeline
```
Get-NlbClusterNodeDip -InputObject <Node[]> [[-IP] <IPAddress>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-NlbClusterNodeDIP** cmdlet gets the dedicated IP address that is requested by the caller.
This IP address is the unique IP address of the local host that is used for dedicated traffic to the host or network traffic that is not associated with the cluster.
Network Load Balancing (NLB) never load balances traffic for the dedicated IP address.
Instead, NLB load balances incoming traffic from all IP addresses other than the dedicated IP address.

## EXAMPLES

### Example 1: List all dedicated IP addresses on the local cluster node
```
PS C:\>Get-NlbClusterNodeDip
Node                       IPAddress                  SubnetMask
----                       ---------                  ----------
Node01                      3.53.4.1                   255.0.0.0
Node01                      fe80::a9cb:eafb:e841:d8cf
Node02                      3.53.4.2                   255.0.0.0
```

This command lists all the dedicated IP addresses on the local cluster node.

### Example 2: List all the dedicated IP addresses on the specified cluster node
```
PS C:\>Get-NlbClusterNodeDip -NodeName "Node02"
Node                       IPAddress                  SubnetMask
----                       ---------                  ----------
Node02                      3.53.4.2                   255.0.0.0
```

This command lists all the dedicated IP addresses on cluster node Node02.

### Example 3: List the dedicated IP address that is specified
```
PS C:\>Get-NlbClusterNodeDip -IP 3.53.4.2
Node                       IPAddress                  SubnetMask
----                       ---------                  ----------
node2                      3.53.4.2                   255.0.0.0
```

This command lists the dedicated IP address specified.

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
Specifies the IP address of the cluster node for which this cmdlet gets the dedicated IP address.

```yaml
Type: IPAddress
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Specifies the node of the cluster for which this cmdlet gets the dedicated IP address.

```yaml
Type: Node[]
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

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NodeName
Specifies the name of the cluster node for which this cmdlet gets the dedicated IP address.

```yaml
Type: String
Parameter Sets: NonPipeline
Aliases: NN

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.NetworkLoadBalancingClusters.PowerShell.Node

## OUTPUTS

### Microsoft.NetworkLoadBalancingClusters.PowerShell.ClusterNodeDip

## NOTES

## RELATED LINKS

[Add-NlbClusterNodeDip](./Add-NlbClusterNodeDip.md)

[Remove-NlbClusterNodeDip](./Remove-NlbClusterNodeDip.md)

[Set-NlbClusterNodeDip](./Set-NlbClusterNodeDip.md)

