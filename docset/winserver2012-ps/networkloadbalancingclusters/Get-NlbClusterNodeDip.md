---
external help file: NLB_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: D1CD4CBF-CCA0-41D1-9DE2-C497199E7A95
manager: dansimp
---

# Get-NlbClusterNodeDip

## SYNOPSIS
Retrieves the dedicated IP address that is queried by the caller.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-NlbClusterNodeDip [[-IP] <IPAddress>] [-HostName <String>] [-InterfaceName <String>] [-NodeName <String>]
```

### UNNAMED_PARAMETER_SET_2
```
Get-NlbClusterNodeDip [[-IP] <IPAddress>] -InputObject <Node>
```

## DESCRIPTION
The **Get-NlbClusterNodeDIP** cmdlet retrieves the dedicated IP address that is requested by the caller.
This IP address is the unique IP address of the local host that is used for dedicated traffic to the host or network traffic that is not associated with the cluster.
Network Load Balancing (NLB) never load balances traffic for the dedicated IP address.
Instead, NLB load balances incoming traffic from all IP addresses other than the dedicated IP address.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-NlbClusterNodeDip
Node                       IPAddress                  SubnetMask 
----                       ---------                  ---------- 
node1                      3.53.4.1                   255.0.0.0 
node1                      fe80::a9cb:eafb:e841:d8cf 
node2                      3.53.4.2                   255.0.0.0
```

This example lists all the dedicated IP addresses on the local cluster node.

### EXAMPLE 2
```
PS C:\>Get-NlbClusterNodeDip -NodeName node2
Node                       IPAddress                  SubnetMask 
----                       ---------                  ---------- 
node2                      3.53.4.2                   255.0.0.0
```

This example lists all the dedicated IP addresses on cluster node node2.

### EXAMPLE 3
```
PS C:\>Get-NlbClusterNodeDip -IP 3.53.4.2
Node                       IPAddress                  SubnetMask 
----                       ---------                  ---------- 
node2                      3.53.4.2                   255.0.0.0
```

This example lists the dedicated IP address specified.

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
Specifies the IP address of the cluster node for which the dedicated IP address is retrieved.

```yaml
Type: IPAddress
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Specifies the node of the cluster for which the dedicated IP address is retrieved.

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

### -NodeName
Specifies the name of the cluster node for which the dedicated IP address is retrieved.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: nn

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

### Microsoft.NetworkLoadBalancingClusters.PowerShell.Node

## OUTPUTS

### Microsoft.NetworkLoadBalancingClusters.PowerShell.ClusterNodeDip

## NOTES

## RELATED LINKS

[Add-NlbClusterNodeDip](./Add-NlbClusterNodeDip.md)

[Remove-NlbClusterNodeDip](./Remove-NlbClusterNodeDip.md)

[Set-NlbClusterNodeDip](./Set-NlbClusterNodeDip.md)

