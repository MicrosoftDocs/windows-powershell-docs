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
The **Set-ClusterParameter** cmdlet controls specific properties of an object in a failover cluster, such as a resource, a group, or a network. 

 -- For a disk resource, you can set the disk signature or GUID of a disk, and turn maintenance on or off for that disk. 

 -- For a Network Name resource, you can set DNS-related information about the resource. 

 -- For an IP address resource, you can set DHCP-related information about the IP Address resource. 

 -- For resources used by virtual machines, you can set details about the settings for the virtual machines.

## EXAMPLES

### Example 1
```
PS C:\> Get-ClusterResource -Name cluster1FS | Set-ClusterParameter -Name HostRecordTTL -Value 300
```

This example configures the clustered resource called cluster1FS on the local cluster, by setting the value of HostRecordTTL to 300.

### Example 2
```
PS C:\> Get-ClusterResource -Name "Cluster IP Address" | Set-ClusterParameter -Multiple @{"Address"="172.24.22.168";"Network"="Cluster Network 2";"EnableDhcp"=1}
```

This example uses the **Multiple** parameter to configure the clustered resource called Cluster IP Address, by setting the **Address**, **Network**, and **EnableDhcp** parameters simultaneously.

### Example 3
```
PS C:\> $res = Get-ClusterResource -Name "IP Address"



PS C:\> $param1 = New-Object -ComObject Microsoft.FailoverClusters.PowerShell.ClusterParameter -Property $res,Address,10.55.88.46



PS C:\> $param2 = New-Object -ComObject Microsoft.FailoverClusters.PowerShell.ClusterParameter -Property $res,SubnetMask,255.0.0.0



PS C:\> $params = $param1,$param2



PS C:\> $params | Set-ClusterParameter
```

This example configures the clustered resource called IP Address to use a new static IP.
Because the new address and subnet mask are required, both parameters must be passed to this cmdlet together.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

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

