---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.FailoverClusters.PowerShell.dll-Help.xml
Module Name: FailoverClusters
ms.date: 11/23/2022
online version: https://learn.microsoft.com/powershell/module/failoverclusters/update-clusteripresource?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Update-ClusterIPResource
---

# Update-ClusterIPResource

## SYNOPSIS
Renews or releases the DHCP lease for an IP address resource in a failover cluster.

## SYNTAX

```
Update-ClusterIPResource [[-Name] <String>] [-Renew] [-Release] [-InputObject <PSObject>]
 [-Cluster <String>] [<CommonParameters>]
```

## DESCRIPTION

The `Update-ClusterIPResource` cmdlet renews or releases the DHCP lease for an IP address resource
in a failover cluster. This cmdlet applies only to IP address resources that use DHCP.

## EXAMPLES

### Example 1: Update DHCP lease

```powershell
Update-ClusterIPResource -Name "Cluster IP Address"
```

This example updates the DHCP lease for the resource called `Cluster IP Address` if this resource is
DHCP assigned.

### Example 2: Update DHCP leases for all clustered IP resources

```powershell
$clusterIP = Get-ClusterResource | Where-Object {$_.ResourceType.Name -eq "IP Address"}
$clusterIP | Update-ClusterIPResource
```

This example updates the DHCP lease for all of the clustered IP resources that are DHCP assigned.

### Example 3: Take a resource offline and release its lease

```powershell
$clusterResource = Get-ClusterResource -Name "IP Address 10.24.11.0"
$clusterResource | Stop-ClusterResource | Update-ClusterIPResource -Release
```

This example takes the resource named `IP Address 172.24.11.0` offline, and releases the DHCP lease
for that resource.

## PARAMETERS

### -Cluster

Specifies the name of the cluster on which to run this cmdlet. If the input for this parameter is
`.` or it is omitted, then the cmdlet runs on the local cluster.

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

### -InputObject

Specifies the cluster IP address resource to update.

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

### -Name

Specifies the name of the cluster IP address resource to update.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Release

Causes the cmdlet to release the DHCP lease of the IP address resource.

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

### -Renew

Causes the cmdlet to renew the DHCP lease of the IP address resource.

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

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.FailoverClusters.PowerShell.ClusterResource

## OUTPUTS

### Microsoft.FailoverClusters.PowerShell.ClusterResource

## NOTES

## RELATED LINKS

[Get-ClusterResource](./Get-ClusterResource.md)

[Update-ClusterNetworkNameResource](./Update-ClusterNetworkNameResource.md)

[Where-Object](https://go.microsoft.com/fwlink/?LinkID=113423)
