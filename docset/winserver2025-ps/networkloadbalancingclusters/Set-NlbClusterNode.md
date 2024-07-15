---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.NetworkLoadBalancingClusters.PowerShell.dll-Help.xml
Module Name: NetworkLoadBalancingClusters
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/networkloadbalancingclusters/set-nlbclusternode?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-NlbClusterNode
---

# Set-NlbClusterNode

## SYNOPSIS
Edits the NLB cluster node settings.

## SYNTAX

### NonPipeline (Default)
```
Set-NlbClusterNode [[-HostName] <String>] -InterfaceName <String> [-Reload] [-HostPriority <Int32>]
 [-InitialHostState <NodeInitialHostState>] [-RetainSuspended <Boolean>] [-Force] [<CommonParameters>]
```

### Pipeline
```
Set-NlbClusterNode -InputObject <Node[]> [-Reload] [-HostPriority <Int32>]
 [-InitialHostState <NodeInitialHostState>] [-RetainSuspended <Boolean>] [-Force] [<CommonParameters>]
```

## DESCRIPTION
The **Set-NlbClusterNode** cmdlet edits the Network Load Balancing (NLB) cluster node settings.
The changes you can make include reconfiguring the host priority, the initial host state, and whether to persist suspended states across reboots.

This operation changes the configuration on all cluster nodes.
As a result, the NLB cluster will have to restart the convergence process on all nodes to guarantee that configuration changes have been applied on all nodes and that a consistent state is reached.
Any additional operations on the NLB cluster should not be initiated until all cluster nodes have completed the convergence process and are back to the converged state.

ps_nlbc_checkstate_remark

## EXAMPLES

### Example 1: Reload the settings of the NLB driver
```
PS C:\>Get-NlbClusterNode -NodeName "Node1" | Set-NlbClusterNode -Reload
Name                State               Interface           HostID
----                -----               ---------           ------
Node1               Converging          vlan-3              1
```

This command instructs the NLB driver on the node named Node1 to reload all of its settings.
This is required if an administrator wants to force configuration changes through the driver.
This cmdlet must be run on Node1 locally.

### Example 2: Set the initial host state of the specified node
```
PS C:\>Get-NlbClusterNode -NodeName "Node1" | Set-NlbClusterNode -InitialHostState Suspended
Name                State               Interface           HostID
----                -----               ---------           ------
Node1               Converging          vlan-3              1
```

This command sets the initial host state of the node named Node1 to Suspended.

### Example 3: Change the persist suspend on the reboot settings on a cluster node
```
PS C:\>Get-NlbClusterNode -NodeName "Node1" | Set-NlbClusterNode -RetainSuspended $True | Format-List -Property "*"
Cluster                   : newcluster
Name                      : node1
InterfaceName             : vlan-3
Host                      : node1.domain.com
State                     : Converging
HostPriority              : 1
AdapterGuid               : {99757561-22EC-44DA-B6D3-82E16B387D6C}
InitialHostState          : Started
PersistSuspendOnReboot    : True
MaskSourceMac             : True
FilterIcmp                : 0
GreDescriptorTimeout      : 10
```

This command changes the persist suspend on reboot setting on node named Node1 to $True.

### Example 4: Change the host priority on a cluster node
```
PS C:\>Get-NlbClusterNode -NodeName "Node1" | Set-NlbClusterNode -HostPriority 5 | Format-List -Property "*"
Cluster                   : newcluster
Name                      : node1
InterfaceName             : vlan-3
Host                      : node1.domain.com
State                     : Converging
HostPriority              : 5
AdapterGuid               : {99757561-22EC-44DA-B6D3-82E16B387D6C}
InitialHostState          : Started
PersistSuspendOnReboot    : True
MaskSourceMac             : True
FilterIcmp                : 0
GreDescriptorTimeout      : 10
```

This command changes the host priority (ID) on the node named Node1 to 5.

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
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HostPriority
Specifies the host priority or host ID for the cluster node.
The acceptable values for this parameter are: 1 through 32.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: Priority, HP

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InitialHostState
Specifies the initial host state for the cluster node.
The acceptable values for this parameter are:

- Started
- Stopped
- Suspended

```yaml
Type: NodeInitialHostState
Parameter Sets: (All)
Aliases: IHS, State
Accepted values: Started, Stopped, Suspended

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Specifies an array of cluster nodes that this cmdlet sets.

```yaml
Type: Node[]
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

### -Reload
Indicates that the cmdlet reloads the NLB driver settings on the current cluster node.
This cmdlet is only valid for the local NLB cluster node and cannot be used to reload a remote NLB cluster node.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: R

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RetainSuspended
Indicates whether the cmdlet sets the new retain suspended setting for the cluster node.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: RS

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.NetworkLoadBalancingClusters.PowerShell.Node

## OUTPUTS

### Microsoft.NetworkLoadBalancingClusters.PowerShell.Node

## NOTES

## RELATED LINKS

[Format-List](https://go.microsoft.com/fwlink/?LinkID=113302)

[Add-NlbClusterNode](./Add-NlbClusterNode.md)

[Get-NlbClusterNode](./Get-NlbClusterNode.md)

[Remove-NlbClusterNode](./Remove-NlbClusterNode.md)

[Resume-NlbClusterNode](./Resume-NlbClusterNode.md)

[Start-NlbClusterNode](./Start-NlbClusterNode.md)

[Stop-NlbClusterNode](./Stop-NlbClusterNode.md)

[Suspend-NlbClusterNode](./Suspend-NlbClusterNode.md)

