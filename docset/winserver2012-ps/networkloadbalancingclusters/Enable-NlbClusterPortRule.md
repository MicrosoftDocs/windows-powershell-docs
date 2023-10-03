---
external help file: NLB_Cmdlets.xml
Module Name: NetworkLoadBalancingClusters
online version: https://learn.microsoft.com/powershell/module/networkloadbalancingclusters/enable-nlbclusterportrule?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Enable-NlbClusterPortRule

## SYNOPSIS
Enables a port rule on a Network Load Balancing (NLB) cluster or on a specific node in the cluster.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Enable-NlbClusterPortRule [-Port] <Nullable> [-ClusterWide] [-HostName <String>] [-InterfaceName <String>]
 [-IP <IPAddress>]
```

### UNNAMED_PARAMETER_SET_2
```
Enable-NlbClusterPortRule -InputObject <PortRule>
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
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

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
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: hn

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
Parameter Sets: UNNAMED_PARAMETER_SET_1
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
Type: PortRule
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue, ByPropertyName)
Accept wildcard characters: False
```

### -InterfaceName
Specifies the interface to which NLB is bound.
This is the interface of the cluster against which this cmdlet is run.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

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
Type: Nullable
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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

