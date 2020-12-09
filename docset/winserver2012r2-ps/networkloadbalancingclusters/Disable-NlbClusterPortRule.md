---
external help file: Microsoft.NetworkLoadBalancingClusters.PowerShell.dll-Help.xml
Module Name: NetworkLoadBalancingClusters
online version: 
schema: 2.0.0
title: Disable-NlbClusterPortRule
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 66A4E053-129E-4218-90DF-C84F1B3E2AB0
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Disable-NlbClusterPortRule

## SYNOPSIS
Disables a port rule on a Network Load Balancing (NLB) cluster or on a specific host in the cluster.

## SYNTAX

### NonPipeline (Default)
```
Disable-NlbClusterPortRule [-Drain] [-Timeout <UInt32>] [-ClusterWide] [-HostName <String>]
 [-InterfaceName <String>] [-IP <IPAddress>] [-Port] <UInt32> [<CommonParameters>]
```

### Pipeline
```
Disable-NlbClusterPortRule -InputObject <PortRule[]> [-Drain] [-Timeout <UInt32>] [<CommonParameters>]
```

## DESCRIPTION
The **Disable-NlbClusterPortRule** cmdlet disables a specific port rule on a Network Load Balancing (NLB) cluster or on a specific host in the NLB cluster.
Disabling new traffic handling should be considered for the port rule using the optional **Drain** parameter.
Specifying the **Drain** parameter at the cluster level drains the specified ports on all hosts within the cluster, and specifying it at the host level drains the ports on the specific host only.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Disable-NlbClusterPortRule -Port 80
IPAddress State     Start     End       Protocol  Mode      Affinity  Timeout 
--------- -----     -----     ---       --------  ----      --------  ------- 
All       Disabled  80        80        Both      Multiple  Single    0
```

This example disables the port rule for port number 80 on the local cluster.

### EXAMPLE 2
```
PS C:\>Get-NlbClusterPortRule | Disable-NlbClusterPortRule
IPAddress State     Start     End       Protocol  Mode      Affinity  Timeout 
--------- -----     -----     ---       --------  ----      --------  ------- 
All       Disabled  80        80        Both      Multiple  Single    0
```

This example disables all port rules on the local cluster.

## PARAMETERS

### -ClusterWide
Disables the given port rule on all cluster nodes.
If this parameter is omitted, then the port rule is only disabled on one node.

```yaml
Type: SwitchParameter
Parameter Sets: NonPipeline
Aliases: Cluster, C

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Drain
Drains existing traffic before disabling this port rule.
If this parameter is omitted, then the existing traffic will be dropped.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: D

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

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
Specifies the IP address for the cluster port rule that will be disabled.

```yaml
Type: IPAddress
Parameter Sets: NonPipeline
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Specifies the cluster port rule to disable.

```yaml
Type: PortRule[]
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

### -Port
Specifies a port number within the port rule that will be disabled.
The acceptable values for this parameter are:`0` through `65535`.

```yaml
Type: UInt32
Parameter Sets: NonPipeline
Aliases: P

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Timeout
Specifies the number of minutes to wait for the drain operation before the port rule is disabled.
After the time expires, the existing connections will be dropped.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: T

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.NetworkLoadBalancingClusters.PowerShell.PortRule

## OUTPUTS

### Microsoft.NetworkLoadBalancingClusters.PowerShell.PortRule

## NOTES

## RELATED LINKS

[Add-NlbClusterPortRule](./Add-NlbClusterPortRule.md)

[Enable-NlbClusterPortRule](./Enable-NlbClusterPortRule.md)

[Get-NlbClusterPortRule](./Get-NlbClusterPortRule.md)

[Remove-NlbClusterPortRule](./Remove-NlbClusterPortRule.md)

[Set-NlbClusterPortRule](./Set-NlbClusterPortRule.md)

