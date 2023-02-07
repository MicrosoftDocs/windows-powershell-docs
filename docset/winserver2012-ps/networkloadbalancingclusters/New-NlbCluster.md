---
external help file: NLB_Cmdlets.xml
Module Name: NetworkLoadBalancingClusters
online version: https://learn.microsoft.com/powershell/module/networkloadbalancingclusters/new-nlbcluster?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# New-NlbCluster

## SYNOPSIS
Creates a Network Load Balancing (NLB) cluster on the specified interface that is defined by the node and network adapter name.

## SYNTAX

```
New-NlbCluster [[-HostName] <String>] [-InterfaceName] <String> [-ClusterPrimaryIP] <IPAddress>
 [-ClusterName <String>] [-DedicatedIP <IPAddress>] [-DedicatedIPSubnetMask <IPAddress>] [-Force]
 [-OperationMode <ClusterMode>] [-SubnetMask <IPAddress>]
```

## DESCRIPTION
The **New-NlbCluster** cmdlet creates a new Network Load Balancing (NLB) cluster.
The following will need to be defined: the node name, the network adapter, primary IP address, dedicated IP address, and the name of the cluster.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>New-NlbCluster -InterfaceName vlan-3 -ClusterPrimaryIP 3.53.100.100 -ClusterName cluster1
Name                IPAddress           SubnetMask          Mode 
----                ---------           ----------          ---- 
cluster1            3.53.100.100        255.0.0.0           UNICAST
```

This example creates a one-node NLB cluster on the current machine.
The created cluster is named cluster1 and has one virtual IP address 3.53.100.100.
This assumes that the interface is not DHCP-enabled.

## PARAMETERS

### -ClusterName
Specifies the name of the new cluster.

```yaml
Type: String
Parameter Sets: (All)
Aliases: name

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ClusterPrimaryIP
Specifies the primary cluster IP address for the new cluster.

```yaml
Type: IPAddress
Parameter Sets: (All)
Aliases: ip, ipaddress, primaryip

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DedicatedIP
Specifies the dedicated IP address to use for the node when creating the new cluster.
If this parameter is omitted, then the existing static IP address on the node will be used.

```yaml
Type: IPAddress
Parameter Sets: (All)
Aliases: dip

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DedicatedIPSubnetMask
Specifies the dedicated IP address subnet mask to use for the node when creating the new cluster.
If this parameter is omitted, then the existing static IP address subnet mask on the node will be used.

```yaml
Type: IPAddress
Parameter Sets: (All)
Aliases: dipsubnetmask

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Runs the cmdlet without prompting for confirmation.
By default the cmdlet will ask for confirmation from the user before proceeding.
This parameter applies if the DHCP setting on the interface needs to be overwritten by the cmdlet.

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
Parameter Sets: (All)
Aliases: hn

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InterfaceName
Specifies the interface to which NLB is bound.
This is the interface of the cluster against which this cmdlet is run.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OperationMode
Specifies the operation mode for the new cluster.
If this parameter is omitted, then the mode is UNICAST.
The acceptable values for this parameter are:IGMPMULTICAST, MULTICAST, or UNICAST.

```yaml
Type: ClusterMode
Parameter Sets: (All)
Aliases: mode

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubnetMask
Specifies the subnet mask for the new cluster primary IP address.

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

## INPUTS

## OUTPUTS

### Microsoft.NetworkLoadBalancingClusters.PowerShell.Cluster

## NOTES

## RELATED LINKS

[Get-NlbCluster](./Get-NlbCluster.md)

[Get-NlbClusterNodeNetworkInterface](./Get-NlbClusterNodeNetworkInterface.md)

[New-NlbClusterIpv6Address](./New-NlbClusterIpv6Address.md)

[Remove-NlbCluster](./Remove-NlbCluster.md)

[Resume-NlbCluster](./Resume-NlbCluster.md)

[Set-NlbCluster](./Set-NlbCluster.md)

[Start-NlbCluster](./Start-NlbCluster.md)

[Stop-NlbCluster](./Stop-NlbCluster.md)

[Suspend-NlbCluster](./Suspend-NlbCluster.md)

