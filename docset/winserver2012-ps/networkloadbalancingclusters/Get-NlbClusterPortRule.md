---
external help file: NLB_Cmdlets.xml
Module Name: NetworkLoadBalancingClusters
online version: https://docs.microsoft.com/powershell/module/networkloadbalancingclusters/get-nlbclusterportrule?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-NlbClusterPortRule

## SYNOPSIS
Retrieves the port rule objects that are queried by the caller.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-NlbClusterPortRule [[-Port] <Nullable>] [-HostName <String>] [-InterfaceName <String>] [-IP <IPAddress>]
 [-NodeName <String>]
```

### UNNAMED_PARAMETER_SET_2
```
Get-NlbClusterPortRule [[-Port] <Nullable>] [-IP <IPAddress>] -InputObject <PSObject>
```

## DESCRIPTION
The **Get-NlbClusterPortRule** cmdlet retrieves the port rules in the Network Load Balancing (NLB) cluster.
If a port number is not specified, all port rules configured for the cluster are listed.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-NlbClusterPortRule
IPAddress State     Start     End       Protocol  Mode      Affinity  Timeout 
--------- -----     -----     ---       --------  ----      --------  ------- 
All       Enabled   0         65535     Both      Multiple  Single    0
```

This example lists all the port rules on the local cluster.

### EXAMPLE 2
```
PS C:\>Get-NlbClusterPortRule -Port 80
IPAddress State     Start     End       Protocol  Mode      Affinity  Timeout 
--------- -----     -----     ---       --------  ----      --------  ------- 
All       Enabled   0         65535     Both      Multiple  Single    0
```

This example gets the port rule that includes port 80.

### EXAMPLE 3
```
PS C:\>Get-NlbClusterNode | Get-NlbClusterPortRule | Format-List -Property *
Cluster          : mycluster 
NodeName         : node1 
VirtualIPAddress : 255.255.255.255 
StartPort        : 0 
EndPort          : 65535 
Affinity         : 
FilteringMode    : Single 
Protocol         : Both 
EqualLoad        : False 
LoadWeight       : 
PortState        : Enabled 
Priority         : 1 
Timeout          : 
 
Cluster          : mycluster 
NodeName         : node2 
VirtualIPAddress : 255.255.255.255 
StartPort        : 0 
EndPort          : 65535 
Affinity         : 
FilteringMode    : Single 
Protocol         : Both 
EqualLoad        : False 
LoadWeight       : 
PortState        : Enabled 
Priority         : 2 
Timeout          :
```

This example gets the port rule from all cluster nodes.
This is especially useful if there are port rules that have Single mode.

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
Specifies the IP address for the cluster port rule that will be retrieved.

```yaml
Type: IPAddress
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Specifies the cluster or cluster node for which port rules are enumerated.

```yaml
Type: PSObject
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

### -NodeName
Specifies the name of the cluster node for which port rules are enumerated.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: nn

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Port
Specifies a port number within the port rule to retrieve.
The acceptable values for this parameter are:`0` through `65535`.

```yaml
Type: Nullable
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

### Microsoft.NetworkLoadBalancingClusters.PowerShell.Cluster

## OUTPUTS

### Microsoft.NetworkLoadBalancingClusters.PowerShell.PortRule

## NOTES

## RELATED LINKS

[Format-List](https://go.microsoft.com/fwlink/?LinkID=113302)

[Add-NlbClusterPortRule](./Add-NlbClusterPortRule.md)

[Disable-NlbClusterPortRule](./Disable-NlbClusterPortRule.md)

[Enable-NlbClusterPortRule](./Enable-NlbClusterPortRule.md)

[Remove-NlbClusterPortRule](./Remove-NlbClusterPortRule.md)

[Set-NlbClusterPortRule](./Set-NlbClusterPortRule.md)

