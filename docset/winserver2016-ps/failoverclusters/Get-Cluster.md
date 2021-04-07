---
author: Kateyanne
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.FailoverClusters.PowerShell.dll-Help.xml
manager: jasgro
Module Name: FailoverClusters
ms.author: v-kaunu
ms.date: 12/20/2016
ms.mktglfcycl: manage
ms.prod: w10
ms.reviewer: 
ms.sitesec: library
ms.technology: 
ms.topic: reference
online version: https://docs.microsoft.com/powershell/module/failoverclusters/get-cluster?view=windowsserver2016-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Cluster
---

# Get-Cluster

## SYNOPSIS
Gets information about one or more failover clusters in a given domain.

## SYNTAX

```
Get-Cluster [[-Name] <String>] [-Domain <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-Cluster** cmdlet gets information about one or more failover clusters in a given domain.

This cmdlet can obtain a variety of configuration and state information about a failover cluster, including the following items: 

 -- State information about whether a backup is in progress. 

 -- State information about whether the cluster is in a forced quorum state. 

 -- Cross-network settings that are especially relevant for multi-site clusters.

To set a common property for the cluster, use this cmdlet to get the cluster object and then set the appropriate property on that cluster object directly.

## EXAMPLES

### Example 1
```
PS C:\> Get-Cluster | Format-List -Property *
Domain                                  : contoso.com 
Name                                    : cluster1 
AddEvictDelay                           : 60 
BackupInProgress                        : 0 
ClusSvcHangTimeout                      : 60 
ClusSvcRegroupOpeningTimeout            : 5 
ClusSvcRegroupPruningTimeout            : 5 
ClusSvcRegroupStageTimeout              : 5 
ClusSvcRegroupTickInMilliseconds        : 300 
ClusterGroupWaitDelay                   : 120 
MinimumNeverPreemptPriority             : 3000 
MinimumPreemptorPriority                : 1 
ClusterEnforcedAntiAffinity             : 0 
ClusterLogLevel                         : 3 
ClusterLogSize                          : 300 
CrossSubnetDelay                        : 1000 
CrossSubnetThreshold                    : 5 
DefaultNetworkRole                      : 2 
Description                             : 
FixQuorum                               : 0 
HangRecoveryAction                      : 3 
IgnorePersistentStateOnStartup          : 0 
LogResourceControls                     : 0 
PlumbAllCrossSubnetRoutes               : 0 
PreventQuorum                           : 0 
QuarantineDuration                      : 7200
QuarantineThreshold                     : 3
QuorumArbitrationTimeMax                : 20 
RequestReplyTimeout                     : 60 
RootMemoryReserved                      : 4294967295 
RouteHistoryLength                      : 0 
SameSubnetDelay                         : 1000 
SameSubnetThreshold                     : 5 
SecurityLevel                           : 1 
SharedVolumeCompatibleFilters           : {} 
SharedVolumeIncompatibleFilters         : {} 
SharedVolumesRoot                       : C:\ClusterStorage 
SharedVolumeSecurityDescriptor          : {1, 0, 4, 128...} 
ShutdownTimeoutInMinutes                : 20 
UseNetftForSharedVolumes                : 1 
UseClientAccessNetworksForSharedVolumes : 0 
SharedVolumeBlockCacheSizeInMB          : 0 
WitnessDatabaseWriteTimeout             : 300 
WitnessRestartInterval                  : 15 
EnableSharedVolumes                     : Enabled 
DynamicQuorum                           : 1 
Id                                      : af5881ef-0ff7-4b5c-bfed-098decbbf762
```

This example displays state and property information for the local cluster in the form of a list.

### Example 2
```
PS C:\> Get-Cluster -Name cluster1
Name 
---- 
cluster1
```

This example gets information about a cluster named cluster1.

### Example 3
```
PS C:\> Get-Cluster -Domain contoso.com
Name 
---- 
cluster1 
cluster2 
cluster3
```

This example gets information about each of the clusters in the contoso.com domain.

### Example 4
```
PS C:\> Get-Cluster | ForEach-Object -Process {$_.CrossSubnetDelay = 1500}
```

This example sets the common property called CrossSubnetDelay for the local cluster to 1500.

### Example 5
```
PS C:\> (Get-Cluster).DynamicQuorum = 1
```

This example enables the Dynamic Quorum feature for the cluster.

### Example 6
```
PS C:\> Get-Cluster | Format-List -Property Quarantine*
QuarantineDuration  : 7200
QuarantineThreshold : 3
```

This example shows default values for QuarantineThreshold and QuarantineDuration for the local cluster.

 -- QuarantineThreshold: This is the number of times that a node can become isolated in an hour before the cluster will be quarantined. This is set to 3 by default.

 --QuarantineDuration: This setting, set to 7200 seconds or 2 hours by default, controls how long a host will remain quarantined.

## PARAMETERS

### -Domain
Specifies the name of the domain in which to enumerate clusters.

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

### -Name
Specifies the name of the cluster to get.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.FailoverClusters.PowerShell.Cluster

## NOTES

## RELATED LINKS

[ForEach-Object](https://go.microsoft.com/fwlink/p/?LinkId=113300)

[Format-List](https://go.microsoft.com/fwlink/p/?LinkId=113302)

[New-Cluster](./New-Cluster.md)

[Remove-Cluster](./Remove-Cluster.md)

[Start-Cluster](./Start-Cluster.md)

[Stop-Cluster](./Stop-Cluster.md)

[Test-Cluster](./Test-Cluster.md)

