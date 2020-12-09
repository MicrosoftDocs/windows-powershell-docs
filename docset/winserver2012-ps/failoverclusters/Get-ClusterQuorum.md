---
external help file: Failoverv2_Cmdlets.xml
online version: 
schema: 2.0.0
ms.assetid: B8B052BB-D0F8-4CC8-9848-0B856C650BA7
manager: dansimp
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Get-ClusterQuorum

## SYNOPSIS
Gets information about the quorum configuration of a failover cluster.

## SYNTAX

```
Get-ClusterQuorum [[-Cluster] <String>] [-InputObject <PSObject>]
```

## DESCRIPTION
The **Get-ClusterQuorum** cmdlet gets information about the quorum configuration of a failover cluster.

The quorum configuration in a failover cluster determines the number of failures that the cluster can sustain.
If an additional failure occurs, then the cluster must stop running.
The relevant failures in this context are failures of nodes or, in some cases, of a disk witness (which contains a copy of the cluster configuration) or file share witness.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-ClusterQuorum
Cluster                    QuorumResource                            QuorumType 
-------                    --------------                            ---------- 
cluster1                   Cluster Disk 1                   NodeAndDiskMajority
```

This example displays the quorum configuration for the local cluster.

### EXAMPLE 2
```
PS C:\>Get-ClusterQuorum -Cluster Cluster1
Cluster                    QuorumResource                            QuorumType 
-------                    --------------                            ---------- 
mycluster                                                          NodeMajority
```

This example displays the quorum configuration for the cluster named Cluster1.

## PARAMETERS

### -Cluster
Specifies the name of the cluster on which to run this cmdlet.
If the input for this parameter is `.` or it is omitted, then the cmdlet runs on the local cluster.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Specifies the cluster for which to query the quorum type.

```yaml
Type: PSObject
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

## INPUTS

### Microsoft.FailoverClusters.PowerShell.Cluster

## OUTPUTS

### Microsoft.FailoverClusters.PowerShell.ClusterQuorumSettings

## NOTES

## RELATED LINKS

[Set-ClusterQuorum](./Set-ClusterQuorum.md)

