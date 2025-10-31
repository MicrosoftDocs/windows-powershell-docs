---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.NetworkLoadBalancingClusters.PowerShell.dll-Help.xml
Module Name: NetworkLoadBalancingClusters
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/networkloadbalancingclusters/set-nlbclusterportrule?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-NlbClusterPortRule
---

# Set-NlbClusterPortRule

## SYNOPSIS
Edits the port rules for a NLB cluster.

## SYNTAX

### NonPipeline (Default)
```
Set-NlbClusterPortRule [-HostName <String>] [-InterfaceName <String>] [-IP <IPAddress>] [[-Port] <UInt32>]
 [-NewIP <IPAddress>] [-NewProtocol <PortRuleProtocol>] [-NewStartPort <Int32>] [-NewEndPort <Int32>]
 [-NewMode <PortRuleFilteringMode>] [-NewAffinity <PortRuleAffinity>] [-NewTimeout <UInt32>]
 [<CommonParameters>]
```

### Pipeline
```
Set-NlbClusterPortRule -InputObject <PortRule[]> [-NewIP <IPAddress>] [-NewProtocol <PortRuleProtocol>]
 [-NewStartPort <Int32>] [-NewEndPort <Int32>] [-NewMode <PortRuleFilteringMode>]
 [-NewAffinity <PortRuleAffinity>] [-NewTimeout <UInt32>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-NlbClusterPortRule** cmdlet edits the port rules for a Network Load Balancing (NLB) cluster.
The port rule configuration you can edit includes the cluster IP address, port range, protocols, filtering mode, affinity, load weight, handling priority, and timeout.

This operation changes the configuration on all cluster nodes.
As a result, the NLB cluster will have to restart the convergence process on all nodes to guarantee that configuration changes have been applied on all nodes and that a consistent state is reached.
Any additional operations on the NLB cluster should not be initiated until all cluster nodes have completed the convergence process and are back to the converged state.

ps_nlbc_checkstate_remark

## EXAMPLES

### Example 1: Change the start port of a port rule
```
PS C:\>Get-NlbClusterPortRule -Port 80 | Set-NlbClusterPortRule -NewStartPort 5
IPAddress State     Start     End       Protocol  Mode      Affinity  Timeout
--------- -----     -----     ---       --------  ----      --------  -------
All       Enabled   5         65535     Both      Multiple  Single    0
```

This command changes the start port of the port rule of port number 80 to 5.

### Example 2: Change the protocol of a port rule
```
PS C:\>Get-NlbClusterPortRule -Port 80 | Set-NlbClusterPortRule -NewProtocol Tcp
IPAddress State     Start     End       Protocol  Mode      Affinity  Timeout
--------- -----     -----     ---       --------  ----      --------  -------
All       Enabled   5         65535     Tcp       Multiple  Single    0
```

This command changes the protocol of the port rule of port number 80 to TCP.

### Example 3: Change the port rule mode
```
PS C:\>Get-NlbClusterPortRule 80 | Set-NlbClusterPortRule -NewMode Single
IPAddress State     Start     End       Protocol  Mode      Affinity  Timeout
--------- -----     -----     ---       --------  ----      --------  -------
All       Enabled   5         65535     Tcp       Single              0
```

This command changes the port rule mode to Single.

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
Specifies the IP address for the cluster port rule to set.

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
Specifies an array of cluster port rules that this cmdlet sets.

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

### -NewAffinity
Specifies the new affinity for the cluster port rule.
The acceptable values for this parameter are:

- Network
- None
- Single

```yaml
Type: PortRuleAffinity
Parameter Sets: (All)
Aliases: NA
Accepted values: None, Single, Network

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NewEndPort
Specifies the new end port for the cluster port rule.
The acceptable values for this parameter are: 0 through 65535.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: NEP

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
Aliases: NIP

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NewMode
Specifies a new mode for the cluster port rule.
The acceptable values for this parameter are:

- Disabled
- Multiple
- Single

```yaml
Type: PortRuleFilteringMode
Parameter Sets: (All)
Aliases: NM
Accepted values: Single, Multiple, Disabled

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NewProtocol
Specifies the new protocol for the cluster port rule.
The acceptable values for this parameter are:

- Both
- Tcp
- Udp

```yaml
Type: PortRuleProtocol
Parameter Sets: (All)
Aliases: NPRTCL
Accepted values: Tcp, Udp, Both

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NewStartPort
Specifies the new start port for the cluster port rule.
The acceptable values for this parameter are: 0 through 65535.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: NSP

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NewTimeout
Specifies the new timeout in minutes for the cluster port rule.
The acceptable values for this parameter are: 0 through 240.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: Timeout, T

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Port
Specifies a port number within the port rule to set.
The acceptable values for this parameter are: 0 through 65535.

```yaml
Type: UInt32
Parameter Sets: NonPipeline
Aliases: P

Required: False
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

[Enable-NlbClusterPortRule](./Enable-NlbClusterPortRule.md)

[Get-NlbClusterPortRule](./Get-NlbClusterPortRule.md)

[Remove-NlbClusterPortRule](./Remove-NlbClusterPortRule.md)

