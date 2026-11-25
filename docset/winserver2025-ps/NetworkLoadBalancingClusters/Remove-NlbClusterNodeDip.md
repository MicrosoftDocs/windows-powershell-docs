---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.NetworkLoadBalancingClusters.PowerShell.dll-Help.xml
Module Name: NetworkLoadBalancingClusters
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/networkloadbalancingclusters/remove-nlbclusternodedip?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-NlbClusterNodeDip
---

# Remove-NlbClusterNodeDip

## SYNOPSIS
Removes a dedicate IP address from a NLB cluster.

## SYNTAX

### NonPipeline (Default)
```
Remove-NlbClusterNodeDip [-PassThru] [-Force] [-HostName <String>] [-InterfaceName <String>] [-IP] <IPAddress>
 [<CommonParameters>]
```

### Pipeline
```
Remove-NlbClusterNodeDip -InputObject <ClusterNodeDip[]> [-PassThru] [-Force] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-NlbClusterNodeDIP** cmdlet removes a dedicate IP address from a Network Load Balancing (NLB) cluster.
Once a dedicated IP address is removed, the node is not accessible through this IP address.

This cmdlet changes the configuration on all cluster nodes.
As a result, the NLB cluster will restart the convergence process on all nodes to guarantee that configuration changes have been applied on all nodes and that a consistent state is reached.
Any additional operations on the NLB cluster is not initiated until all cluster nodes have completed the convergence process and are back to the converged state.

ps_nlbc_checkstate_remark

## EXAMPLES

### Example 1: Remove the dedicated IP address from the local cluster with confirmation
```
PS C:\>Remove-NlbClusterNodeDip -IP fe80::9bf9:2019:372a:ca5
```

This command removes the dedicated IP address from the local cluster after seeking confirmation from the user.

### Example 2: Remove the dedicated IP address from the local cluster without confirmation
```
PS C:\>Remove-NlbClusterNodeDip -IP fe80::9bf9:2019:372a:ca5 -Force
```

This command removes the dedicated IP address from the local cluster.
Because the Force parameter is used, the command does not seek confirmation from the user.

### Example 3: Remove the specified dedicated IP address from the remote host
```
PS C:\>Remove-NlbClusterNodeDip -IP fe80::8cb4:defa:65b2:8983 -HostName "Node002"
```

This example removes the dedicated IP address from the remote host named Node002.

## PARAMETERS

### -Force
Forces the command to run without asking for user confirmation.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: F

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
Specifies the IP address for the cluster node from which this cmdlet removes the dedicated IP address.

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
Specifies an array of cluster node dedicated IP addresses that this cmdlet removes.

```yaml
Type: ClusterNodeDip[]
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

### -PassThru
Sends items from the interactive window down the pipeline as input to other cmdlets.
By default, this cmdlet does not generate any output.
To send items from the interactive window down the pipeline, click to select the items and then click OK.
Shift-click and Ctrl-click are supported.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: Pass

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.NetworkLoadBalancingClusters.PowerShell.ClusterNodeDip

## OUTPUTS

### Microsoft.NetworkLoadBalancingClusters.PowerShell.ClusterNodeDip

## NOTES

## RELATED LINKS

[Add-NlbClusterNodeDip](./Add-NlbClusterNodeDip.md)

[Get-NlbClusterNodeDip](./Get-NlbClusterNodeDip.md)

[Set-NlbClusterNodeDip](./Set-NlbClusterNodeDip.md)

