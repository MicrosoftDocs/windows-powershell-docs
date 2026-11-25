---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.NetworkLoadBalancingClusters.PowerShell.dll-Help.xml
Module Name: NetworkLoadBalancingClusters
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/networkloadbalancingclusters/get-nlbclusterdriverinfo?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-NlbClusterDriverInfo
---

# Get-NlbClusterDriverInfo

## SYNOPSIS
Gets information about the Network Load Balancing (NLB) driver on the local machine.

## SYNTAX

### Params (Default)
```
Get-NlbClusterDriverInfo [-InterfaceName <String>] [-Params] [<CommonParameters>]
```

### Filter
```
Get-NlbClusterDriverInfo [-InterfaceName <String>] -Filter <Protocol> -ClientIP <IPAddress>
 [-ClientPort <Int32>] -ServerIP <IPAddress> [-ServerPort <Int32>] [-Flags <Flags>] [<CommonParameters>]
```

### ConvergenceHistory
```
Get-NlbClusterDriverInfo [-InterfaceName <String>] [-ConvergenceHistory] [<CommonParameters>]
```

### ExtendedAffinityList
```
Get-NlbClusterDriverInfo [-InterfaceName <String>] [-ExtendedAffinityList] [<CommonParameters>]
```

### ExtendedAffinityExceptionList
```
Get-NlbClusterDriverInfo [-InterfaceName <String>] [-ExtendedAffinityExceptionList] [<CommonParameters>]
```

### OpenConnections
```
Get-NlbClusterDriverInfo [-InterfaceName <String>] [-OpenConnections] [<CommonParameters>]
```

## DESCRIPTION
The **Get-NlbClusterDriverInfo** cmdlet gets information about the Network Load Balancing (NLB) driver on the local machine.
This includes information about IP addresses, ports, convergence history, connections, extended affinity status, and protocols.

## EXAMPLES

### Example 1: Get information about the NLB driver configuration
```
PS C:\>Get-NlbClusterDriverInfo
FullyQualifiedDomainName : cluster1.contoso.com
ParametersVersion        : 6
EffectiveNlbVersion      : 513
HostId                   : 2
ClusterName              : cluster1
ClusterIPAddress         : 2001:4898:e8:3018:bd82:dde1:6615:7b0
ClusterMacAddress        : 02-BF-FB-7E-A2-D1
AliveMsgPeriod           : 1000
MaxConnectionDescriptors : 262144
IcmpFilteringEnabled     : False
InitialHostState         : Started
CurrentHostState         : Started
PersistedHostStates      : True
```

This command gets information about the NLB driver configuration.

### Example 2: Get the history of convergence for the local node
```
PS C:\>Get-NlbClusterDriverInfo -ConvergenceHistory
Time                       FromState                  ToState
----                       ---------                  -------
11/5/2008 10:55:27 PM      StablePhase2               Converged
11/5/2008 10:55:26 PM      ConvergingPhase2           StablePhase2
11/5/2008 10:55:26 PM      StablePhase1               ConvergingPhase2
11/5/2008 10:55:20 PM      ConvergingPhase1           StablePhase1
11/5/2008 10:55:17 PM      Unknown                    ConvergingPhase1
```

This command gets the history of convergence for the local node.

### Example 3: Declare whether traffic in the given pattern is accepted on the local node
```
PS C:\>Get-NlbClusterDriverInfo -Filter TCP -ServerIP 2.53.4.222 -ServerPort 5001 -ClientIP 2.53.4.5 -ClientPort 5001
Result
------
ACCEPT_UNCONDITIONAL_OWNERSHIP
```

This command declares whether traffic in the given pattern is accepted on the local node or not.

### Example 4: Enumerate the client IP addresses that are on the extended affinity list on the cluster node
```
PS C:\>Get-NlbClusterDriverInfo -ExtendedAffinityList
IPAddress           References          VirtualIPAddress    StartPort
---------           ----------          ----------------    ---------
2.53.4.5            0                   All                 0
2.53.4.6            0                   All                 0
2.53.4.7            1                   All                 0
```

This command enumerates the client IP addresses that are on the extended affinity list on this cluster node.
This applies to port rules that have extended affinity timeout enabled.
The cmdlet also displays the number of active connections for each client.

### Example 5: Enumerate the client IP addresses that are on the extended affinity exception list
```
PS C:\>Get-NlbClusterDriverInfo -ExtendedAffinityExceptionList
IPAddress           HostId              VirtualIPAddress    StartPort
---------           ------              ----------------    ---------
2.53.4.6            2                   All                 0
```

This command enumerates the client IP addresses that are on the extended affinity exception list.
This applies to port rules that have extended affinity timeout enabled.
Traffic from clients on this list will be picked up by another cluster node that has the host ID listed.

### Example 6: Enumerate all open connections on the cluster node
```
PS C:\>Get-NlbClusterDriverInfo -OpenConnections
SourceIPAddress     SourcePort          DestinationIPAddres DestinationPorts

---------------     ----------          ------------------- ---------------
2.53.4.5            64945               2.53.4.222          5001
2.53.4.15           64854               2.53.4.222          80
```

This command enumerates all open connections on this cluster node.
This is useful to run when the draining operation takes a long time and the administrator wants to know which connections are on the node.

## PARAMETERS

### -ClientIP
Specifies the connection client IP address that is used to check whether the current cluster node accepts or drops the traffic.

```yaml
Type: IPAddress
Parameter Sets: Filter
Aliases: CIP

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ClientPort
Specifies the connection tuple client port that is used to check whether the current cluster node accepts or drops the traffic.
The acceptable values for this parameter are: 0 through 65535.

```yaml
Type: Int32
Parameter Sets: Filter
Aliases: CPT

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ConvergenceHistory
Indicates that the cmdlet gets the history of convergences between the cluster nodes.

```yaml
Type: SwitchParameter
Parameter Sets: ConvergenceHistory
Aliases: History

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExtendedAffinityExceptionList
Indicates that the cmdlet gets the extended affinity exception list on this cluster node.

```yaml
Type: SwitchParameter
Parameter Sets: ExtendedAffinityExceptionList
Aliases: ExceptionList

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExtendedAffinityList
Indicates that the cmdlet gets the extended affinity list on this cluster node.

```yaml
Type: SwitchParameter
Parameter Sets: ExtendedAffinityList
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Filter
Specifies whether or not a certain traffic pattern is picked by this cluster node.
The parameter specifies the protocol that is used to check whether the current cluster node accepts or drops the traffic.
The acceptable values for this parameter are:

- Gre
- Icmp
- Ipsec
- Pptp
- Tcp
- Udp

```yaml
Type: Protocol
Parameter Sets: Filter
Aliases:
Accepted values: Tcp, Pptp, Gre, Udp, Ipsec, Icmp

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Flags
Specifies the type of packet that is used to check whether the current cluster node accepts or drops the traffic.
The acceptable values for this parameter are:

- Fin
- Rst
- Syn

```yaml
Type: Flags
Parameter Sets: Filter
Aliases: FG
Accepted values: Syn, Fin, Rst

Required: False
Position: Named
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

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OpenConnections
Indicates that the cmdlet gets the list of open connections to the cluster.

```yaml
Type: SwitchParameter
Parameter Sets: OpenConnections
Aliases: OpenConnection

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Params
Indicates that the cmdlet gets the list information about the NLB driver on this node.

```yaml
Type: SwitchParameter
Parameter Sets: Params
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServerIP
Specifies the connection tuple server IP address used to check whether the current cluster node accepts or drops the traffic.

```yaml
Type: IPAddress
Parameter Sets: Filter
Aliases: SIP

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServerPort
Specifies the connection tuple server port used to check whether the current cluster node accepts or drops the traffic.
The acceptable values for this parameter are: 0 through 65535.

```yaml
Type: Int32
Parameter Sets: Filter
Aliases: SPT

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.NetworkLoadBalancingClusters.PowerShell.ClientExceptionRecord

### Microsoft.NetworkLoadBalancingClusters.PowerShell.ClusterSettings

### Microsoft.NetworkLoadBalancingClusters.PowerShell.ConvergenceHistoryRecord

### Microsoft.NetworkLoadBalancingClusters.PowerShell.DescriptorRecord

### Microsoft.NetworkLoadBalancingClusters.PowerShell.DriverInfo

### Microsoft.NetworkLoadBalancingClusters.PowerShell.ExtendedAffinityRecord

## NOTES

## RELATED LINKS

[Get-NlbCluster](./Get-NlbCluster.md)

[Get-NlbClusterNode](./Get-NlbClusterNode.md)

