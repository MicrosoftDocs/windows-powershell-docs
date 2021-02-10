---
external help file:
Module Name: hpc
online version:
schema: 2.0.0
title: Get-HpcNetworkTopology
description:
keywords: powershell, cmdlet
ms.date: 12/20/2016
ms.prod: powershell
ms.topic: reference
online version: http://go.microsoft.com/fwlink/?LinkId=182659
schema: 2.0.0
ms.assetid: B0D29FB7-E5E3-466A-8247-05A7151F1734
manager: dansimp
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Get-HpcNetworkTopology

## SYNOPSIS
Gets the current network topology for the HPC cluster.

## SYNTAX

```
Get-HpcNetworkTopology [-Scheduler <String[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-HpcNetworkTopology** cmdlet gets the current network topology for the HPC cluster.
The network topology can be Enterprise, Private, EnterprisePrivate, PrivateApplication, or EnterprisePrivateApplication.
These topologies are defined as follows:

- Enterprise. All nodes are connected only to an enterprise network. You only must have one network adapter on the head node for this topology.
- Private. The compute nodes are isolated on a private network. You must have two network adapters on the head node for this topology.
- EnterprisePrivate. All nodes are connected to both enterprise and private networks. You must have two network adapters on the head node for this topology.
- PrivateApplication. The compute nodes are isolated on private and application networks. You must have three network adapters on the head node for this topology.
- EnterprisePrivateApplication. All nodes are connected to enterprise, private, and application networks. You must have three network adapters on the head node for this topology.

## EXAMPLES

### Example 1: Get the current topology
```
PS C:\>Get-HpcNetworkTopology
```

This command gets the current network topology for the HPC cluster.

## PARAMETERS

### -Scheduler
Specifies the host name or IP address of the head node for the cluster for which you want to get the network topology.
The value must be a valid computer name or IP address.
If you do not specify the *Scheduler* parameter, this cmdlet uses the scheduler on the head node that the CCP_SCHEDULER environment variable specifies.
To set this environment variable, run the following cmdlet:

`Set-Content Env:CCP_SCHEDULER \<head_node_name\>`

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### None

## NOTES
* You must be a cluster administrator to run this cmdlet successfully.

## RELATED LINKS

