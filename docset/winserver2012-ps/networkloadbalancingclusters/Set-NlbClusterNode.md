---
author: Kateyanne
external help file: NLB_Cmdlets.xml
manager: dansimp
Module Name: NetworkLoadBalancingClusters
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/networkloadbalancingclusters/set-nlbclusternode?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-NlbClusterNode

## SYNOPSIS
Edits the Network Load Balancing (NLB) cluster node settings.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Set-NlbClusterNode [[-HostName] <String>] [-Force] [-HostPriority <Nullable>] [-InitialHostState <Nullable>]
 [-Reload] [-RetainSuspended <Nullable>] -InterfaceName <String>
```

### UNNAMED_PARAMETER_SET_2
```
Set-NlbClusterNode [-Force] [-HostPriority <Nullable>] [-InitialHostState <Nullable>] [-Reload]
 [-RetainSuspended <Nullable>] -InputObject <Node>
```

## DESCRIPTION
The **Set-NlbClusterNode** cmdlet edits the Network Load Balancing (NLB) cluster node settings.
The changes you can make include reconfiguring the host priority, the initial host state, and whether to persist suspended states across reboots.

This operation changes the configuration on all cluster nodes.
As a result, the NLB cluster will have to restart the convergence process on all nodes to guarantee that configuration changes have been applied on all nodes and that a consistent state is reached.
Any additional operations on the NLB cluster should not be initiated until all cluster nodes have completed the convergence process and are back to the converged state.

ps_nlbc_checkstate_remark

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-NlbClusterNode -NodeName node1 | Set-NlbClusterNode -Reload
Name                State               Interface           HostID 
----                -----               ---------           ------ 
node1               Converging          vlan-3              1
```

This example instructs the NLB driver on the node named node1 to reload all of its settings.
This is required if an administrator wants to force configuration changes through the driver.
This cmdlet must be run on node1 locally.

### EXAMPLE 2
```
PS C:\>Get-NlbClusterNode -NodeName node1 | Set-NlbClusterNode -InitialHostState Suspended
Name                State               Interface           HostID 
----                -----               ---------           ------ 
node1               Converging          vlan-3              1
```

This example sets the initial host state of the node named node1 to Suspended.

### EXAMPLE 3
```
PS C:\>Get-NlbClusterNode -NodeName node1| Set-NlbClusterNode -RetainSuspended $TRUE | Format-List -Property *
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

This example changes the persist suspend on reboot setting on node named node1 to TRUE.

### EXAMPLE 4
```
PS C:\>Get-NlbClusterNode -NodeName node1 | Set-NlbClusterNode -HostPriority 5 | Format-List -Property *
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

This example changes the host priority (ID) on the node named node1 to 5.

## PARAMETERS

### -Force
Runs the cmdlet without prompting for confirmation.
By default the cmdlet will ask for confirmation from the user before proceeding.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
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
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HostPriority
Specifies the host priority or host ID for the cluster node.
The acceptable values for this parameter are:`1` through `32`.

```yaml
Type: Nullable
Parameter Sets: (All)
Aliases: hp, priority

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InitialHostState
Specifies the initial host state for the cluster node.
The acceptable values for this parameter are:Started, Stopped, or Suspended.

```yaml
Type: Nullable
Parameter Sets: (All)
Aliases: ihs, state

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Specifies the cluster node to set.

```yaml
Type: Node
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

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Reload
Causes the NLB driver on the current cluster node to load its settings.
This cmdlet is only valid for the local NLB cluster node and cannot be used to reload a remote NLB cluster node.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RetainSuspended
Specifies the new retain suspended setting for the cluster node.

```yaml
Type: Nullable
Parameter Sets: (All)
Aliases: rs

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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

