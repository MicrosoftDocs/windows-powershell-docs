---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-anbarr
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.FailoverClusters.PowerShell.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Add-ClusterGroup
ms.reviewer:
ms.assetid: 558598BD-965C-4FFD-A3C3-BF862221C5CB
---

# Add-ClusterGroup

## SYNOPSIS
Adds an empty resource group to the failover cluster configuration, in preparation for adding clustered resources to the group.

## SYNTAX

```
Add-ClusterGroup [-Name] <StringCollection> [[-GroupType] <GroupType>] [-InputObject <PSObject>]
 [-Cluster <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Add-ClusterGroup** cmdlet adds an empty resource group to the failover cluster configuration, in preparation for adding clustered resources to the group.
A resource group, or a clustered role, is the unit of failover.
During failover, all resources in the resource group move together.

## EXAMPLES

### Example 1: Add a resource group
```
PS C:\> Add-ClusterGroup -Name "Group1"
Name                       OwnerNode                                      State 
----                       ---------                                      ----- 
Group1                     node1                                         Online
```

This example adds an empty resource group called Group1 to the failover cluster.

## PARAMETERS

### -Cluster
Specifies the name of the cluster on which to run this cmdlet.
If the input for this parameter is `.` or it is omitted, then the cmdlet runs on the local cluster.

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

### -GroupType
Specifies the type of group to add to the failover cluster configuration.

```yaml
Type: GroupType
Parameter Sets: (All)
Aliases: 
Accepted values: Cluster, AvailableStorage, Temporary, ClusterSharedVolume, ClusterStoragePool, FileServer, DhcpServer, Dtc, Msmq, Wins, StandAloneDfs, GenericApplication, GenericService, GenericScript, IScsiNameService, VirtualMachine, TsSessionBroker, IScsiTarget, ScaleoutFileServer, VMReplicaBroker, TaskScheduler, Unknown

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Specifies the cluster on which to create the resource group.

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

### -Name
Specifies the name of the resource group to add.

```yaml
Type: StringCollection
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.FailoverClusters.PowerShell.Cluster

## OUTPUTS

### Microsoft.FailoverClusters.PowerShell.ClusterGroup

## NOTES

## RELATED LINKS

[Get-ClusterGroup](./Get-ClusterGroup.md)

[Move-ClusterGroup](./Move-ClusterGroup.md)

[Remove-ClusterGroup](./Remove-ClusterGroup.md)

[Start-ClusterGroup](./Start-ClusterGroup.md)

[Stop-ClusterGroup](./Stop-ClusterGroup.md)

