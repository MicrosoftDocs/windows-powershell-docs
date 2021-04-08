---
author: Kateyanne
external help file: NLB_Cmdlets.xml
manager: dansimp
Module Name: NetworkLoadBalancingClusters
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/networkloadbalancingclusters/set-nlbclusterportrule?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-NlbClusterPortRule

## SYNOPSIS
Edits the port rules for a Network Load Balancing (NLB) cluster.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Set-NlbClusterPortRule [[-Port] <Nullable>] [-HostName <String>] [-InterfaceName <String>] [-IP <IPAddress>]
 [-NewAffinity <Nullable>] [-NewEndPort <Nullable>] [-NewIP <IPAddress>] [-NewMode <Nullable>]
 [-NewProtocol <Nullable>] [-NewStartPort <Nullable>] [-NewTimeout <Nullable>]
```

### UNNAMED_PARAMETER_SET_2
```
Set-NlbClusterPortRule [-NewAffinity <Nullable>] [-NewEndPort <Nullable>] [-NewIP <IPAddress>]
 [-NewMode <Nullable>] [-NewProtocol <Nullable>] [-NewStartPort <Nullable>] [-NewTimeout <Nullable>]
 -InputObject <PortRule>
```

## DESCRIPTION
The **Set-NlbClusterPortRule** cmdlet edits the port rules for a Network Load Balancing (NLB) cluster.
The port rule configuration you can edit includes the cluster IP address, port range, protocols, filtering mode, affinity, load weight, handling priority, and timeout.

This operation changes the configuration on all cluster nodes.
As a result, the NLB cluster will have to restart the convergence process on all nodes to guarantee that configuration changes have been applied on all nodes and that a consistent state is reached.
Any additional operations on the NLB cluster should not be initiated until all cluster nodes have completed the convergence process and are back to the converged state.

ps_nlbc_checkstate_remark

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-NlbClusterPortRule -Port 80 | Set-NlbClusterPortRule -NewStartPort 5
IPAddress State     Start     End       Protocol  Mode      Affinity  Timeout 
--------- -----     -----     ---       --------  ----      --------  ------- 
All       Enabled   5         65535     Both      Multiple  Single    0
```

This example changes the start port of the port rule of port number 80 to 5.

### EXAMPLE 2
```
PS C:\>Get-NlbClusterPortRule -Port 80 | Set-NlbClusterPortRule -NewProtocol Tcp
IPAddress State     Start     End       Protocol  Mode      Affinity  Timeout 
--------- -----     -----     ---       --------  ----      --------  ------- 
All       Enabled   5         65535     Tcp       Multiple  Single    0
```

This command changes the protocol of the port rule of port number 80 to TCP.

### EXAMPLE 3
```
PS C:\>Get-NlbClusterPortRule 80 | Set-NlbClusterPortRule -NewMode Single
IPAddress State     Start     End       Protocol  Mode      Affinity  Timeout 
--------- -----     -----     ---       --------  ----      --------  ------- 
All       Enabled   5         65535     Tcp       Single              0
```

This example changes the port rule mode to Single.

## PARAMETERS

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
Specifies the IP address for the cluster port rule to set.

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
Specifies the cluster port rule to set.

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

### -NewAffinity
Specifies the new affinity for the cluster port rule.
The acceptable values for this parameter are:Network, None, and Single.

```yaml
Type: Nullable
Parameter Sets: (All)
Aliases: na

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NewEndPort
Specifies the new end port for the cluster port rule.
The acceptable values for this parameter are:`0` through `65535`.

```yaml
Type: Nullable
Parameter Sets: (All)
Aliases: nep

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NewIP
Specifies the new IP address for the cluster port rule.

```yaml
Type: IPAddress
Parameter Sets: (All)
Aliases: nip

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NewMode
Specifies a new mode for the cluster port rule.
The acceptable values for this parameter are:Disabled, Multiple hosts, and Single host.

```yaml
Type: Nullable
Parameter Sets: (All)
Aliases: nm

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NewProtocol
Specifies the new protocol for the cluster port rule.
The acceptable values for this parameter are:Both, Tcp, and Udp.

```yaml
Type: Nullable
Parameter Sets: (All)
Aliases: nprtcl

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NewStartPort
Specifies the new start port for the cluster port rule.
The acceptable values for this parameter are:`0` through `65535`.

```yaml
Type: Nullable
Parameter Sets: (All)
Aliases: nsp

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NewTimeout
Specifies the new timeout in minutes for the cluster port rule.
The acceptable values for this parameter are:`0` through `240`.

```yaml
Type: Nullable
Parameter Sets: (All)
Aliases: t

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Port
Specifies a port number within the port rule to set.
The acceptable values for this parameter are:`0` through `65535`.

```yaml
Type: Nullable
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
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

[Enable-NlbClusterPortRule](./Enable-NlbClusterPortRule.md)

[Get-NlbClusterPortRule](./Get-NlbClusterPortRule.md)

[Remove-NlbClusterPortRule](./Remove-NlbClusterPortRule.md)

