---
external help file: Microsoft.NetworkLoadBalancingClusters.PowerShell.dll-Help.xml
Module Name: NetworkLoadBalancingClusters
online version: 
schema: 2.0.0
title: Get-NlbClusterVip
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 89BF641C-ED3A-4FEF-AA25-23AD3BE7003F
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Get-NlbClusterVip

## SYNOPSIS
Retrieves virtual IP addresses that are queried by the caller.

## SYNTAX

### NonPipeline (Default)
```
Get-NlbClusterVip [-HostName <String>] [-InterfaceName <String>] [[-IP] <IPAddress>] [<CommonParameters>]
```

### Pipeline
```
Get-NlbClusterVip -InputObject <Cluster[]> [[-IP] <IPAddress>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-NlbClusterVIP** cmdlet retrieves the virtual IP addresses that are queried by the caller.
This IP address is used to address the cluster as a whole, and is the IP address that maps to the full Internet name that you specify for the Network Load Balancing (NLB) cluster.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-NlbClusterVip
IPAddress                               SubnetMask 
---------                               ---------- 
3.53.100.100                            255.0.0.0 
3.53.100.101                            255.0.0.0 
3.53.100.102                            255.0.0.0 
fe80::b349:6945:9449:d03c               ::
```

This example lists all the virtual IP addresses on the local cluster.

### EXAMPLE 2
```
PS C:\>Get-NlbClusterVip -IP fe80::a20f:cca:4cd2:7ea0
IPAddress                               SubnetMask 
---------                               ---------- 
fe80::a20f:cca:4cd2:7ea0               ::
```

This example gets the specified virtual IP addresses on the local cluster.

## PARAMETERS

### -HostName
Specifies the name of the cluster host against which this cmdlet is run.
If this parameter is omitted or a value of `.` is entered, then the local cluster is assumed.

```yaml
Type: String
Parameter Sets: NonPipeline
Aliases: Host, HN, H

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IP
Specifies the IP address of the cluster for which the virtual IP address is enumerated.

```yaml
Type: IPAddress
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Specifies the cluster for which the virtual IP address is enumerated.

```yaml
Type: Cluster[]
Parameter Sets: Pipeline
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -InterfaceName
Specifies the interface to which NLB is bound.
This is the interface of the cluster against which this cmdlet is run.

```yaml
Type: String
Parameter Sets: NonPipeline
Aliases: Interface, IN, I

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.NetworkLoadBalancingClusters.PowerShell.Cluster

## OUTPUTS

### Microsoft.NetworkLoadBalancingClusters.PowerShell.ClusterVip

## NOTES

## RELATED LINKS

[Add-NlbClusterVip](./Add-NlbClusterVip.md)

[Remove-NlbClusterVip](./Remove-NlbClusterVip.md)

[Set-NlbClusterVip](./Set-NlbClusterVip.md)

