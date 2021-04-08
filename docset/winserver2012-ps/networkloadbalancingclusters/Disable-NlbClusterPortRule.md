---
author: Kateyanne
external help file: NLB_Cmdlets.xml
manager: dansimp
Module Name: NetworkLoadBalancingClusters
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/networkloadbalancingclusters/disable-nlbclusterportrule?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Disable-NlbClusterPortRule

## SYNOPSIS
Disables a port rule on a Network Load Balancing (NLB) cluster or on a specific host in the cluster.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Disable-NlbClusterPortRule [-Port] <Nullable> [-ClusterWide] [-Drain] [-HostName <String>]
 [-InterfaceName <String>] [-IP <IPAddress>] [-Timeout <Nullable>]
```

### UNNAMED_PARAMETER_SET_2
```
Disable-NlbClusterPortRule [-Drain] [-Timeout <Nullable>] -InputObject <PortRule>
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
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

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
Aliases: 

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
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: hn

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
Parameter Sets: UNNAMED_PARAMETER_SET_1
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
Specifies a port number within the port rule that will be disabled.
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

### -Timeout
Specifies the number of minutes to wait for the drain operation before the port rule is disabled.
After the time expires, the existing connections will be dropped.

```yaml
Type: Nullable
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
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

[Enable-NlbClusterPortRule](./Enable-NlbClusterPortRule.md)

[Get-NlbClusterPortRule](./Get-NlbClusterPortRule.md)

[Remove-NlbClusterPortRule](./Remove-NlbClusterPortRule.md)

[Set-NlbClusterPortRule](./Set-NlbClusterPortRule.md)

