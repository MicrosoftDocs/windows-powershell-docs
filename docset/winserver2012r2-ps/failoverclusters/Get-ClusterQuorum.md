---
external help file: Microsoft.FailoverClusters.PowerShell.dll-Help.xml
Module Name: FailoverClusters
online version: 
schema: 2.0.0
title: Get-ClusterQuorum
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
ms.assetid: B8B052BB-D0F8-4CC8-9848-0B856C650BA7
---

# Get-ClusterQuorum

## SYNOPSIS
Gets information about the quorum configuration of a failover cluster.

## SYNTAX

```
Get-ClusterQuorum [[-Cluster] <String>] [-InputObject <PSObject>] [<CommonParameters>]
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
Position: 0
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.FailoverClusters.PowerShell.Cluster

## OUTPUTS

### Microsoft.FailoverClusters.PowerShell.ClusterQuorumSettings

## NOTES

## RELATED LINKS

[Set-ClusterQuorum](./Set-ClusterQuorum.md)

