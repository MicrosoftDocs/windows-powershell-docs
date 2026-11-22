---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.NetworkLoadBalancingClusters.PowerShell.dll-Help.xml
Module Name: NetworkLoadBalancingClusters
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/networkloadbalancingclusters/set-nlbclustervip?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-NlbClusterVip
---

# Set-NlbClusterVip

## SYNOPSIS
Edits the virtual IP address of a NLB cluster.

## SYNTAX

### NonPipeline (Default)
```
Set-NlbClusterVip [-HostName <String>] -InterfaceName <String> [-IP] <IPAddress> -NewIP <IPAddress>
 [<CommonParameters>]
```

### Pipeline
```
Set-NlbClusterVip -InputObject <ClusterVip[]> -NewIP <IPAddress> [<CommonParameters>]
```

## DESCRIPTION
The **Set-NlbClusterVIP** cmdlet edits the virtual IP address of a Network Load Balancing (NLB) cluster.
This cmdlet can be used to edit the IP address and subnet mask for the virtual IP address.

This operation changes the configuration on all cluster nodes.
As a result, the NLB cluster restarts the convergence process on all nodes to guarantee that configuration changes have been applied on all nodes and that a consistent state is reached.
Any additional operations on the NLB cluster should not be initiated until all cluster nodes have completed the convergence process and are back to the converged state.

ps_nlbc_checkstate_remark

## EXAMPLES

### Example 1: Change the cluster virtual IP address
```
PS C:\>Get-NlbClusterVip -IP fe80::ad1c:c26a:b9d2:5679 | Set-NlbClusterVip -NewIP fe80::ae34:85b1:d7e9:d51f
IPAddress                               SubnetMask
---------                               ----------
fe80::ae34:85b1:d7e9:d51f                ::
```

This command changes the cluster virtual IP from fe80::ad1c:c26a:b9d2:5679 to fe80::ae34:85b1:d7e9:d51f.

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
Specifies the IP address of the cluster for which this cmdlet sets the virtual IP address.

```yaml
Type: IPAddress
Parameter Sets: NonPipeline
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Specifies an array of cluster virtual IP address that this cmdlet sets.

```yaml
Type: ClusterVip[]
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

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NewIP
Specifies the new virtual IP address for the cluster.

```yaml
Type: IPAddress
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.NetworkLoadBalancingClusters.PowerShell.ClusterVip

## OUTPUTS

### Microsoft.NetworkLoadBalancingClusters.PowerShell.ClusterVip

## NOTES

## RELATED LINKS

[Add-NlbClusterVip](./Add-NlbClusterVip.md)

[Get-NlbClusterVip](./Get-NlbClusterVip.md)

[Remove-NlbClusterVip](./Remove-NlbClusterVip.md)

