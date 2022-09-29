---
external help file: Microsoft.NetworkLoadBalancingClusters.PowerShell.dll-Help.xml
Module Name: NetworkLoadBalancingClusters
ms.date: 10/30/2017
online version: https://learn.microsoft.com/powershell/module/networkloadbalancingclusters/enable-nlbclusterportrule?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-NlbClusterPortRule
---

# Enable-NlbClusterPortRule

## SYNOPSIS
Enables a port rule on a Network Load Balancing (NLB) cluster or on a specific node in the cluster.

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

### EXAMPLE 1
```
PS C:\>Enable-NlbClusterPortRule -Port 80
IPAddress State     Start     End       Protocol  Mode      Affinity  Timeout 
--------- -----     -----     ---       --------  ----      --------  ------- 
All       Enabled   80        80        Both      Multiple  Single    0
```

This example enables port rule 80 on the local cluster.

### EXAMPLE 2
```
PS C:\>Get-NlbClusterPortRule | Enable-NlbClusterPortRule
IPAddress State     Start     End       Protocol  Mode      Affinity  Timeout 
--------- -----     -----     ---       --------  ----      --------  ------- 
All       Enabled   80        80        Both      Multiple  Single    0
```

This example enables all port rules on the local cluster.

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
Specifies the IP address for the cluster port rule that will be enabled.

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
Specifies the cluster port rule to enable.

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
Specifies a port number within the port rule that will be enabled.
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

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

