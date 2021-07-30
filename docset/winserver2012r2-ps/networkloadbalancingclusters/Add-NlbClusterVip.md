---
external help file: Microsoft.NetworkLoadBalancingClusters.PowerShell.dll-Help.xml
Module Name: NetworkLoadBalancingClusters
ms.date: 10/30/2017
online version: https://docs.microsoft.com/powershell/module/networkloadbalancingclusters/add-nlbclustervip?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-NlbClusterVip
---

# Add-NlbClusterVip

## SYNOPSIS
Adds a virtual IP address to a Network Load Balancing (NLB) cluster.

## SYNTAX

### NonPipeline (Default)
```
Add-NlbClusterVip [-IP] <IPAddress> [-SubnetMask <IPAddress>] [-HostName <String>] -InterfaceName <String>
 [<CommonParameters>]
```

### Pipeline
```
Add-NlbClusterVip -InputObject <Cluster[]> [-IP] <IPAddress> [-SubnetMask <IPAddress>] [<CommonParameters>]
```

## DESCRIPTION
The **Add-NlbClusterVIP** cmdlet adds a virtual IP address to a Network Load Balancing (NLB) cluster.
The virtual IP address will appear on all hosts in the cluster.
This IP address is used to address the cluster as a whole, and it should be the IP address that maps to the full Internet name that you specify for the cluster.

This cmdlet changes the configuration on all cluster nodes.
As a result, the NLB cluster will have to restart the convergence process on all nodes to guarantee that configuration changes have been applied on all nodes and that a consistent state is reached.
Any additional operations on the NLB cluster should not be initiated until all cluster nodes have completed the convergence process and are back to the converged state.

ps_nlbc_checkstate_remark

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Add-NlbClusterVip -IP fe80::94dc:5e59:3626:f1d4 -InterfaceName vlan-3
IPAddress                               SubnetMask 
---------                               ---------- 
fe80::94dc:5e59:3626:f1d4               ::
```

This example adds an IPv6 IP address to the list of virtual NLB cluster IP addresses on the network interface vlan-3.

### EXAMPLE 2
```
PS C:\>Get-NlbCluster | Add-NlbClusterVip -IP fe80::94dc:5e59:3626:f1d4
IPAddress                               SubnetMask 
---------                               ---------- 
fe80::94dc:5e59:3626:f1d4               ::
```

This example adds an IPv6 IP address to the list of virtual NLB cluster IP addresses on the local cluster.

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
Specifies the IP address of the new cluster to which the virtual IP address is added.

```yaml
Type: IPAddress
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Specifies the cluster to which the cluster virtual IP address is added.

```yaml
Type: Cluster[]
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

### -SubnetMask
Specifies the subnet mask for the virtual IP address of the new cluster.

```yaml
Type: IPAddress
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.NetworkLoadBalancingClusters.PowerShell.Cluster

## OUTPUTS

### Microsoft.NetworkLoadBalancingClusters.PowerShell.ClusterVip

## NOTES

## RELATED LINKS

[Get-NlbClusterVip](./Get-NlbClusterVip.md)

[Remove-NlbClusterVip](./Remove-NlbClusterVip.md)

[Set-NlbClusterVip](./Set-NlbClusterVip.md)

