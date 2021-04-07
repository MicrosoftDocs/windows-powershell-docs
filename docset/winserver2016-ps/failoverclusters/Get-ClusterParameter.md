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
online version: https://docs.microsoft.com/powershell/module/failoverclusters/get-clusterparameter?view=windowsserver2016-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ClusterParameter
---

# Get-ClusterParameter

## SYNOPSIS
Gets detailed information about an object in a failover cluster, such as a cluster resource.

## SYNTAX

```
Get-ClusterParameter [[-Name] <StringCollection>] [-InputObject <PSObject>] [-Cluster <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-ClusterParameter** cmdlet gets detailed information about an object in a failover cluster, such as a cluster resource.
This cmdlet is used to manage private properties for a cluster object.
To get and set common properties for a cluster object, use the appropriate Get-Cluster* cmdlet to get the cluster object of interest and then set the property of interest on that cluster object directly.

The type of detailed information you can obtain with this cmdlet depends on the cmdlet you combine with it.
For example: 

- If you use this cmdlet with the **Get-ClusterResource** cmdlet for a disk resource, then you can obtain the disk signature or GUID of a disk and information about whether maintenance is turned on for that disk. 

- If you use this cmdlet with the **Get-ClusterResource** cmdlet for a Network Name resource, then you can obtain DNS-related information about the resource. 

- If you use this cmdlet with the **Get-ClusterResource** cmdlet for an IP address resource, then you can obtain DHCP-related information about the IP Address resource. 

- If you use this cmdlet with the **Get-ClusterResource** cmdlet for resources used by virtual machines, then you can obtain details about the settings for the virtual machines.

## EXAMPLES

### Example 1
```
PS C:\> Get-ClusterResource -Name cluster1FS | Get-ClusterParameter
Object              Name                Value               Type 
------              ----                -----               ---- 
cluster1FS          Name                cluster1FS          String 
cluster1FS          DnsName             cluster1FS          String 
cluster1FS          RemapPipeNames      0                   UInt32 
cluster1FS          HostRecordTTL       1200                UInt32 
cluster1FS          RegisterAllProvi... 0                   UInt32 
cluster1FS          PublishPTRRecords   0                   UInt32 
cluster1FS          TimerCallbackAdd... 5                   UInt32 
cluster1FS          ResourceData        {1, 0, 0, 0...}     ByteArray 
cluster1FS          StatusNetBIOS       0                   UInt32 
cluster1FS          StatusDNS           0                   UInt32 
cluster1FS          StatusKerberos      0                   UInt32 
cluster1FS          CreatingDC          \\DOMAIN12-DC-05... String 
cluster1FS          LastDNSUpdateTime   10/15/2008 9:50:... DateTime 
cluster1FS          ObjectGUID          8054680893fd5943... String
```

This example gets the parameters, including the detailed information, for the cluster resource named cluster1FS on the local cluster.
The displayed parameters will vary according to the type of resource being viewed.

### Example 2
```
PS C:\> Get-ClusterResource -Name cluster1FS | Get-ClusterParameter -Name HostRecordTTL
Object              Name                Value               Type 
------              ----                -----               ---- 
cluster1FS          HostRecordTTL       1200                UInt32
```

This example displays the HostRecordTTL parameter for the cluster resource named cluster1FS on the local cluster, if that parameter is applicable to cluster1FS.

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
Specifies the cluster object for which to get more information.

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
Specifies the name of the cluster parameter to get.

```yaml
Type: StringCollection
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

### Microsoft.FailoverClusters.PowerShell.Cluster

### Microsoft.FailoverClusters.PowerShell.ClusterGroup

### Microsoft.FailoverClusters.PowerShell.ClusterNetwork

### Microsoft.FailoverClusters.PowerShell.ClusterNetworkInterface

### Microsoft.FailoverClusters.PowerShell.ClusterNode

### Microsoft.FailoverClusters.PowerShell.ClusterResource

### Microsoft.FailoverClusters.PowerShell.ClusterResourceType

### Microsoft.FailoverClusters.PowerShell.ClusterSharedVolume

## OUTPUTS

### Microsoft.FailoverClusters.PowerShell.ClusterParameter

## NOTES

## RELATED LINKS

[Set-ClusterParameter](./Set-ClusterParameter.md)

