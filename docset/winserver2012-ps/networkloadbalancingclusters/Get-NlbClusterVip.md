---
external help file: NLB_Cmdlets.xml
Module Name: NetworkLoadBalancingClusters
online version: https://learn.microsoft.com/powershell/module/networkloadbalancingclusters/get-nlbclustervip?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-NlbClusterVip

## SYNOPSIS
Retrieves virtual IP addresses that are queried by the caller.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-NlbClusterVip [[-IP] <IPAddress>] [-HostName <String>] [-InterfaceName <String>]
```

### UNNAMED_PARAMETER_SET_2
```
Get-NlbClusterVip [[-IP] <IPAddress>] -InputObject <Cluster>
```

## DESCRIPTION
The **Get-NlbClusterVIP** cmdlet retrieves the virtual IP addresses that are queried by the caller.
This IP address is used to address the cluster as a whole, and is the IP address that maps to the full Internet name that you specify for the Network Load Balancing (NLB) cluster.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-NlbClusterVip
IPAddress                               SubnetMask 
---------                               ---------- 
3.53.100.100                            255.0.0.0 
3.53.100.101                            255.0.0.0 
3.53.100.102                            255.0.0.0 
fe80::b349:6945:9449:d03c               ::
```

This example lists all the virtual IP addresses on the local cluster.

### EXAMPLE 2
```
PS C:\>Get-NlbClusterVip -IP fe80::a20f:cca:4cd2:7ea0
IPAddress                               SubnetMask 
---------                               ---------- 
fe80::a20f:cca:4cd2:7ea0               ::
```

This example gets the specified virtual IP addresses on the local cluster.

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
Specifies the IP address of the cluster for which the virtual IP address is enumerated.

```yaml
Type: IPAddress
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Specifies the cluster for which the virtual IP address is enumerated.

```yaml
Type: Cluster
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

## INPUTS

### Microsoft.NetworkLoadBalancingClusters.PowerShell.Cluster

## OUTPUTS

### Microsoft.NetworkLoadBalancingClusters.PowerShell.ClusterVip

## NOTES

## RELATED LINKS

[Add-NlbClusterVip](./Add-NlbClusterVip.md)

[Remove-NlbClusterVip](./Remove-NlbClusterVip.md)

[Set-NlbClusterVip](./Set-NlbClusterVip.md)

