---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.NetworkLoadBalancingClusters.PowerShell.dll-Help.xml
Module Name: NetworkLoadBalancingClusters
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/networkloadbalancingclusters/enable-nlbclusterportrule?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-NlbClusterPortRule
---

# Enable-NlbClusterPortRule

## SYNOPSIS
Enables a port rule on a NLB cluster or on a specific node in the cluster.

## SYNTAX

### NonPipeline (Default)
```
Enable-NlbClusterPortRule [-ClusterWide] [-HostName <String>] [-InterfaceName <String>] [-IP <IPAddress>]
 [-Port] <UInt32> [<CommonParameters>]
```

### Pipeline
```
Enable-NlbClusterPortRule -InputObject <PortRule[]> [<CommonParameters>]
```

## DESCRIPTION
The **Enable-NlbClusterPortRule** cmdlet enables a specific port rule on a Network Load Balancing (NLB) cluster or on a specific node in the NLB cluster.

## EXAMPLES

### Example 1: Enable a port rule on the local cluster
```
PS C:\>Enable-NlbClusterPortRule -Port 80
IPAddress State     Start     End       Protocol  Mode      Affinity  Timeout
--------- -----     -----     ---       --------  ----      --------  -------
All       Enabled   80        80        Both      Multiple  Single    0
```

This command enables port rule 80 on the local cluster.

### Example 2: Enable all port rules on the local cluster
```
PS C:\>Get-NlbClusterPortRule | Enable-NlbClusterPortRule
IPAddress State     Start     End       Protocol  Mode      Affinity  Timeout
--------- -----     -----     ---       --------  ----      --------  -------
All       Enabled   80        80        Both      Multiple  Single    0
```

This command enables all port rules on the local cluster.

## PARAMETERS

### -ClusterWide
Enables the given port rule on all cluster nodes.
If this parameter is omitted, then the port rule is only enabled on one node.

```yaml
Type: SwitchParameter
Parameter Sets: NonPipeline
Aliases: Cluster, C

Required: False
Position: Named
Default value: None
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
Specifies the IP address for the cluster port rule that this cmdlet enables.

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
Specifies an array of cluster port rules that this cmdlet enables.

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
Specifies a port number within the port rule that is enabled.
The acceptable values for this parameter are: 0 through 65535.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.NetworkLoadBalancingClusters.PowerShell.PortRule

## OUTPUTS

### Microsoft.NetworkLoadBalancingClusters.PowerShell.PortRule

## NOTES

## RELATED LINKS

[Add-NlbClusterPortRule](./Add-NlbClusterPortRule.md)

[Disable-NlbClusterPortRule](./Disable-NlbClusterPortRule.md)

[Get-NlbClusterPortRule](./Get-NlbClusterPortRule.md)

[Remove-NlbClusterPortRule](./Remove-NlbClusterPortRule.md)

[Set-NlbClusterPortRule](./Set-NlbClusterPortRule.md)

