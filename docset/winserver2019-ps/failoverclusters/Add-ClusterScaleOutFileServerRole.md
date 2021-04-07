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
online version: https://docs.microsoft.com/powershell/module/failoverclusters/add-clusterscaleoutfileserverrole?view=windowsserver2019-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-ClusterScaleOutFileServerRole
---

# Add-ClusterScaleOutFileServerRole

## SYNOPSIS
Creates a clustered file server for scale-out application data.

## SYNTAX

```
Add-ClusterScaleOutFileServerRole [[-Name] <String>] [-Wait <Int32>] [-InputObject <PSObject>]
 [-Cluster <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Add-ClusterScaleOutFileServerRole** cmdlet creates a clustered file server for scale-out application data.
A file server for scale-out application data provides storage for applications or virtual machines that leave files open for extended periods of time.
Client connections are distributed across nodes for better throughput.
This type of file server supports the Server Message Block (SMB) protocol.
It does not support the Network File System (NFS) protocol, or certain role services such as File Server Resource Manager (FSRM) or Distributed File System (DFS) Replication.

Note: This cmdlet cannot be run remotely without Credential Security Service Provider (CredSSP) authentication on the server computer.

## EXAMPLES

### Example 1
```
PS C:\> Add-ClusterScaleOutFileServerRole
Name                                    OwnerNode                               State 
----                                    ---------                               ----- 
clusterSOFS                             CLUSTER-N2                              Online
```

This example creates a highly available Scale-out file server role.

### Example 2
```
PS C:\> Add-ClusterScaleOutFileServerRole -Wait 0
Name                                    OwnerNode                               State 
----                                    ---------                               ----- 
clusterSOFS                             CLUSTER-N2                              Pending
```

This example creates a highly available scale out file server role.
The cmdlet completes without waiting for all resources to come online.

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

### -InputObject
Specifies the cluster on which to create the highly available scale-out file server.

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
Specifies the name of the highly available scale-out file server being created.

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

### -Wait
Specifies the time in seconds to wait for the cmdlet.
If the **Wait** parameter is not specified, then the cmdlet waits for completion.
If `-Wait 0` is specified, then the call is initiated and the cmdlet returns without waiting.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.FailoverClusters.PowerShell.Cluster

## OUTPUTS

### Microsoft.FailoverClusters.PowerShell.ClusterGroup

## NOTES

## RELATED LINKS

[Add-ClusterFileServerRole](./Add-ClusterFileServerRole.md)

[Get-ClusterGroup](./Get-ClusterGroup.md)

[Move-ClusterGroup](./Move-ClusterGroup.md)

[Remove-ClusterGroup](./Remove-ClusterGroup.md)

[Start-ClusterGroup](./Start-ClusterGroup.md)

[Stop-ClusterGroup](./Stop-ClusterGroup.md)

