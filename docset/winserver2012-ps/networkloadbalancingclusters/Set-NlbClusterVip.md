---
external help file: NLB_Cmdlets.xml
Module Name: NetworkLoadBalancingClusters
online version: https://docs.microsoft.com/powershell/module/networkloadbalancingclusters/set-nlbclustervip?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-NlbClusterVip

## SYNOPSIS
Edits the virtual IP address of a Network Load Balancing (NLB) cluster.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Set-NlbClusterVip [-IP] <IPAddress> [-HostName <String>] -InterfaceName <String> -NewIP <IPAddress>
```

### UNNAMED_PARAMETER_SET_2
```
Set-NlbClusterVip -InputObject <ClusterVip> -NewIP <IPAddress>
```

## DESCRIPTION
The **Set-NlbClusterVIP** cmdlet edits the virtual IP address of a Network Load Balancing (NLB) cluster.
This cmdlet can be used to edit the IP address and subnet mask for the virtual IP address.

This operation changes the configuration on all cluster nodes.
As a result, the NLB cluster will have to restart the convergence process on all nodes to guarantee that configuration changes have been applied on all nodes and that a consistent state is reached.
Any additional operations on the NLB cluster should not be initiated until all cluster nodes have completed the convergence process and are back to the converged state.

ps_nlbc_checkstate_remark

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-NlbClusterVip -IP fe80::ad1c:c26a:b9d2:5679 | Set-NlbClusterVip -NewIP fe80::ae34:85b1:d7e9:d51f
IPAddress                               SubnetMask 
---------                               ---------- 
fe80::ae34:85b1:d7e9:d51f                ::
```

This example changes the cluster virtual IP from fe80::ad1c:c26a:b9d2:5679 to fe80::ae34:85b1:d7e9:d51f.

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
Specifies the IP address of the cluster for which the virtual IP address will be set.

```yaml
Type: IPAddress
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Specifies the cluster virtual IP address to set.

```yaml
Type: ClusterVip
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

## INPUTS

### Microsoft.NetworkLoadBalancingClusters.PowerShell.ClusterVip

## OUTPUTS

### Microsoft.NetworkLoadBalancingClusters.PowerShell.ClusterVip

## NOTES

## RELATED LINKS

[Add-NlbClusterVip](./Add-NlbClusterVip.md)

[Get-NlbClusterVip](./Get-NlbClusterVip.md)

[Remove-NlbClusterVip](./Remove-NlbClusterVip.md)

