---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.FailoverClusters.PowerShell.dll-Help.xml
Module Name: FailoverClusters
ms.date: 12/20/2016
online version: https://docs.microsoft.com/powershell/module/failoverclusters/set-clusterparameter?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-ClusterParameter
---

# Set-ClusterParameter

## SYNOPSIS
Controls specific properties of an object in a failover cluster, such as a resource, a group, or a network.

## SYNTAX

### NoMultiple (Default)
```
Set-ClusterParameter [-InputObject <PSObject>] [-Create] [-Delete] [-Cluster <String>] [<CommonParameters>]
```

### Single Parameter
```
Set-ClusterParameter [-InputObject <PSObject>] [[-Name] <String>] [[-Value] <PSObject>] [-Create] [-Delete]
 [-Cluster <String>] [<CommonParameters>]
```

### Multiple Parameter
```
Set-ClusterParameter [-InputObject <PSObject>] [[-Multiple] <Hashtable>] [-Create] [-Delete]
 [-Cluster <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-ClusterParameter** cmdlet controls specific properties of an object in a failover cluster,
such as a resource, a group, or a network.

 -- For a disk resource, you can set the disk signature or GUID of a disk, and turn maintenance on
 or off for that disk.

 -- For a Network Name resource, you can set DNS-related information about the resource.

 -- For an IP address resource, you can set DHCP-related information about the IP Address resource. 

 -- For resources used by virtual machines, you can set details about the settings for the virtual
 machines.

## EXAMPLES

### Example 1
```powershell
Get-ClusterResource -Name cluster1FS | Set-ClusterParameter -Name HostRecordTTL -Value 300
```

This example configures the clustered resource called cluster1FS on the local cluster, by setting
the value of HostRecordTTL to 300.

### Example 2
```powershell
$parameters = @{
    Multiple = @{'Address'='10.1.100.12';
		        'SubnetMask'='255.255.255.0';
                'Network'='Cluster Network 1';
                'EnableDhcp'='0'}
}
Get-ClusterResource -Name "Cluster IP Address" | Set-ClusterParameter @parameters
```

This example configures the clustered resource called IP Address to use a new static IP using the
`Multiple` parameter to configure the clustered resource called Cluster IP Address, by setting the
`Address`, `SubnetMask`, `Network`, and `EnableDhcp` parameters simultaneously.

This example uses splatting to pass parameter values from the `$Parameters` variable to the command.
Learn more about [Splatting](/powershell/module/microsoft.powershell.core/about/about_splatting).

## PARAMETERS

### -Cluster


```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Create


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

### -Delete


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

### -InputObject


```yaml
Type: PSObject
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Multiple


```yaml
Type: Hashtable
Parameter Sets: Multiple Parameter
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name


```yaml
Type: String
Parameter Sets: Single Parameter
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Value


```yaml
Type: PSObject
Parameter Sets: Single Parameter
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.FailoverClusters.PowerShell.Cluster

### Microsoft.FailoverClusters.PowerShell.ClusterGroup

### Microsoft.FailoverClusters.PowerShell.ClusterNetwork

### Microsoft.FailoverClusters.PowerShell.ClusterNetworkInterface

### Microsoft.FailoverClusters.PowerShell.ClusterNode

### Microsoft.FailoverClusters.PowerShell.ClusterParameter

### Microsoft.FailoverClusters.PowerShell.ClusterResource

### Microsoft.FailoverClusters.PowerShell.ClusterResourceType

### Microsoft.FailoverClusters.PowerShell.ClusterSharedVolume

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Get-ClusterParameter](./Get-ClusterParameter.md)

