---
author: Kateyanne
external help file: NLB_Cmdlets.xml
manager: dansimp
Module Name: NetworkLoadBalancingClusters
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/networkloadbalancingclusters/get-nlbclusterdriverinfo?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-NlbClusterDriverInfo

## SYNOPSIS
Retrieves information about the Network Load Balancing (NLB) driver on the local machine.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-NlbClusterDriverInfo [-InterfaceName <String>] [-Params]
```

### UNNAMED_PARAMETER_SET_2
```
Get-NlbClusterDriverInfo [-ClientPort <Int32>] [-Flags <Flags>] [-InterfaceName <String>] [-ServerPort <Int32>]
 -ClientIP <IPAddress> -Filter <Protocol> -ServerIP <IPAddress>
```

### UNNAMED_PARAMETER_SET_3
```
Get-NlbClusterDriverInfo [-InterfaceName <String>] [-ConvergenceHistory]
```

### UNNAMED_PARAMETER_SET_4
```
Get-NlbClusterDriverInfo [-InterfaceName <String>] [-ExtendedAffinityExceptionList]
```

### UNNAMED_PARAMETER_SET_5
```
Get-NlbClusterDriverInfo [-InterfaceName <String>] [-ExtendedAffinityList]
```

### UNNAMED_PARAMETER_SET_6
```
Get-NlbClusterDriverInfo [-InterfaceName <String>] [-OpenConnections]
```

## DESCRIPTION
The **Get-NlbClusterDriverInfo** cmdlet retrieves information about the Network Load Balancing (NLB) driver on the local machine.
This includes information about IP addresses, ports, convergence history, connections, extended affinity status, and protocols.

## EXAMPLES

### EXAMPLE 1
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

This example gets information about the NLB driver configuration.

### EXAMPLE 2
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

This example gets the history of convergence for the local node.

### EXAMPLE 3
```
PS C:\>Get-NlbClusterDriverInfo -Filter TCP -ServerIP 2.53.4.222 -ServerPort 5001 -ClientIP 2.53.4.5 -ClientPort 5001
Result 
------ 
ACCEPT_UNCONDITIONAL_OWNERSHIP
```

This example declares whether traffic in the given pattern will be accepted on the local node or not.

### EXAMPLE 4
```
PS C:\>Get-NlbClusterDriverInfo -ExtendedAffinityList
IPAddress           References          VirtualIPAddress    StartPort 
---------           ----------          ----------------    --------- 
2.53.4.5            0                   All                 0 
2.53.4.6            0                   All                 0 
2.53.4.7            1                   All                 0
```

This example will enumerate the client IP addresses that are on the extended affinity list on this cluster node.
This applies to port rules that have extended affinity timeout enabled.
The cmdlet also displays the number of active connections for each client.

### EXAMPLE 5
```
PS C:\>Get-NlbClusterDriverInfo -ExtendedAffinityExceptionList
IPAddress           HostId              VirtualIPAddress    StartPort 
---------           ------              ----------------    --------- 
2.53.4.6            2                   All                 0
```

This example will enumerate the client IP addresses that are on the extended affinity exception list.
This applies to port rules that have extended affinity timeout enabled.
Traffic from clients on this list will be picked up by another cluster node that has the host ID listed.

### EXAMPLE 6
```
PS C:\>Get-NlbClusterDriverInfo -OpenConnections
SourceIPAddress     SourcePort          DestinationIPAddres DestinationPorts

---------------     ----------          ------------------- --------------- 
2.53.4.5            64945               2.53.4.222          5001 
2.53.4.15           64854               2.53.4.222          80
```

This example enumerates all open connections on this cluster node.
This is useful to run when the draining operation takes a long time and the administrator wants to know which connections are on the node.

## PARAMETERS

### -ClientIP
Specifies the connection client IP address that is used to check whether the current cluster node accepts or drops the traffic.

```yaml
Type: IPAddress
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: cip

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ClientPort
Specifies the connection tuple client port that is used to check whether the current cluster node accepts or drops the traffic.
The acceptable values for this parameter are:`0` through `65535`.

```yaml
Type: Int32
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: cpt

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ConvergenceHistory
Gets the history of convergences between the cluster nodes.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: history

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExtendedAffinityExceptionList
Gets the extended affinity exception list on this cluster node.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_4
Aliases: exceptionlist

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExtendedAffinityList
Gets the extended affinity list on this cluster node.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_5
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Filter
Determines whether or not a certain traffic pattern will be picked by this cluster node.
The parameter specifies the protocol that is used to check whether the current cluster node accepts or drops the traffic.
The acceptable values for this parameter are:TCP or UDP.

```yaml
Type: Protocol
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Flags
Specifies the type of packet that is used to check whether the current cluster node accepts or drops the traffic.
The acceptable values for this parameter are:SYN FIN or RST.

```yaml
Type: Flags
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: fg

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
Gets the list of open connections to the cluster.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_6
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Params
Gets the list information about the NLB driver on this node.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_1
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
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: sip

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServerPort
Specifies the connection tuple server port used to check whether the current cluster node accepts or drops the traffic.
The acceptable values for this parameter are:`0` through `65535`.

```yaml
Type: Int32
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: spt

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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

