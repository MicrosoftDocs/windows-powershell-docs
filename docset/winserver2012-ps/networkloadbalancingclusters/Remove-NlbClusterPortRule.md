---
external help file: NLB_Cmdlets.xml
Module Name: NetworkLoadBalancingClusters
online version: https://docs.microsoft.com/powershell/module/networkloadbalancingclusters/remove-nlbclusterportrule?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Remove-NlbClusterPortRule

## SYNOPSIS
Removes a port rule from a Network Load Balancing (NLB) cluster.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Remove-NlbClusterPortRule [[-Port] <Nullable>] [-Force] [-HostName <String>] [-PassThru]
 -InterfaceName <String> -IP <IPAddress>
```

### UNNAMED_PARAMETER_SET_2
```
Remove-NlbClusterPortRule [-Force] [-PassThru] -InputObject <PortRule>
```

## DESCRIPTION
The **Remove-NlbClusterPortRule** cmdlet removes a port rule from a Network Load Balancing (NLB) cluster.
Port rules control how an NLB cluster functions.
To maximize the control of various types of TCP/IP traffic, port rules can be set up to control how each port's cluster-network traffic is handled.
The number and type of port rules must be exactly the same for each node in the cluster.
If a node attempts to join the cluster with a different number of rules or with different rules from the other nodes, then it is not accepted as part of the cluster.

This cmdlet changes the configuration on all cluster nodes.
As a result, the NLB cluster will have to restart the convergence process on all nodes to guarantee that configuration changes have been applied on all nodes and that a consistent state is reached.
Any additional operations on the NLB cluster should not be initiated until all cluster nodes have completed the convergence process and are back to the converged state.

ps_nlbc_checkstate_remark

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-NlbClusterPortRule -Port 4 | Remove-NlbClusterPortRule
```

This example deletes the port rule for port number 4 on the local cluster.

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
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IP
Specifies the IP address for the cluster port rule to remove.

```yaml
Type: IPAddress
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Specifies the cluster port rule to remove.

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

Required: True
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
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Port
Specifies a port number within the port rule to remove.
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

[Set-NlbClusterPortRule](./Set-NlbClusterPortRule.md)

