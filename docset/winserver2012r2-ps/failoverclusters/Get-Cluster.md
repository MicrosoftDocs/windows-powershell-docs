---
external help file: Microsoft.FailoverClusters.PowerShell.dll-Help.xml
Module Name: FailoverClusters
online version: 
schema: 2.0.0
title: Get-Cluster
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 4A2838C2-64AA-40D8-8BB9-A6993A7E1F47
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

### EXAMPLE 1
```
PS C:\>Get-Cluster | Format-List -Property *
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

### EXAMPLE 2
```
PS C:\>Get-Cluster -Name cluster1
Name 
---- 
cluster1
```

This example gets information about a cluster named cluster1.

### EXAMPLE 3
```
PS C:\>Get-Cluster -Domain contoso.com
Name 
---- 
cluster1 
cluster2 
cluster3
```

This example gets information about each of the clusters in the contoso.com domain.

### EXAMPLE 4
```
PS C:\> Get-Cluster | ForEach-Object -Process {$_.CrossSubnetDelay = 1500}
```

This example sets the common property called CrossSubnetDelay for the local cluster to 1500.

### EXAMPLE 5
```
PS C:\>(Get-Cluster).DynamicQuorum = 1
```

This example enables the Dynamic Quorum feature for the cluster.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

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

