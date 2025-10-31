---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.NetworkLoadBalancingClusters.PowerShell.dll-Help.xml
Module Name: NetworkLoadBalancingClusters
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/networkloadbalancingclusters/get-nlbclusterportrule?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-NlbClusterPortRule
---

# Get-NlbClusterPortRule

## SYNOPSIS
Gets the port rule objects that are queried by the caller.

## SYNTAX

### NonPipeline (Default)
```
Get-NlbClusterPortRule [-HostName <String>] [-InterfaceName <String>] [-IP <IPAddress>] [[-Port] <UInt32>]
 [-NodeName <String>] [<CommonParameters>]
```

### Pipeline
```
Get-NlbClusterPortRule -InputObject <PSObject[]> [-IP <IPAddress>] [[-Port] <UInt32>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-NlbClusterPortRule** cmdlet gets the port rules in the Network Load Balancing (NLB) cluster.
If a port number is not specified, all port rules configured for the cluster are listed.

## EXAMPLES

### Example 1: List all port rules on the local cluster
```
PS C:\>Get-NlbClusterPortRule
IPAddress State     Start     End       Protocol  Mode      Affinity  Timeout
--------- -----     -----     ---       --------  ----      --------  -------
All       Enabled   0         65535     Both      Multiple  Single    0
```

This command lists all the port rules on the local cluster.

### Example 2: Get a port rule for a specific port
```
PS C:\>Get-NlbClusterPortRule -Port 80
IPAddress State     Start     End       Protocol  Mode      Affinity  Timeout
--------- -----     -----     ---       --------  ----      --------  -------
All       Enabled   0         65535     Both      Multiple  Single    0
```

This command gets the port rule that includes port 80.

### Example 3: Get port rules from all cluster nodes
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

This command gets the port rule from all cluster nodes.
This is especially useful if there are port rules that have Single mode.

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
Specifies the IP address for the cluster port rule that this cmdlet gets.

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
Specifies an array of cluster or cluster nodes for which port rules are enumerated.

```yaml
Type: PSObject[]
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

### -NodeName
Specifies the name of the cluster node for which port rules are enumerated.

```yaml
Type: String
Parameter Sets: NonPipeline
Aliases: NN

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Port
Specifies a port number within the port rule that this cmdlet gets.
The acceptable values for this parameter are: 0 through 65535.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

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

