---
external help file: Failoverv2_Cmdlets.xml
online version: 
schema: 2.0.0
ms.assetid: 7172BC57-F26A-4132-AB0D-87DBCBAADAA9
manager: dansimp
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Update-ClusterIPResource

## SYNOPSIS
Renews or releases the DHCP lease for an IP address resource in a failover cluster.

## SYNTAX

```
Update-ClusterIPResource [[-Name] <String>] [-Cluster <String>] [-InputObject <PSObject>] [-Release] [-Renew]
```

## DESCRIPTION
The **Update-ClusterIPResource** cmdlet renews or releases the DHCP lease for an IP address resource in a failover cluster.
This cmdlet applies only to IP address resources that use DHCP.

## EXAMPLES

### Example 1
```
PS C:\>Update-ClusterIPResource -Name "Cluster IP Address"
Name                State               Group               ResourceType 
----                -----               -----               ------------ 
Cluster IP Address  Online              Cluster Group       IP Address
```

This example updates the DHCP lease for the resource called Cluster IP Address if this resource is DHCP assigned.

### Example 2
```
PS C:\>Get-ClusterResource | Where-Object -FilterScript {$_.ResourceType.Name -eq "IP Address"} | Update-ClusterIPResource
Name                State               Group               ResourceType 
----                -----               -----               ------------ 
Cluster IP Address  Online              Cluster Group       IP Address 
IP Address 172.2... Online              cluster1-Other      IP Address 
IP Address 172.2... Online              cluster1-FS         IP Address
```

This example updates the DHCP lease for all of the clustered IP resources that are DHCP assigned.

### Example 3
```
PS C:\>Get-ClusterResource -Name "IP Address 172.24.11.0" | Stop-ClusterResource | Update-ClusterIPResource -Release
Name                State               Group               ResourceType 
----                -----               -----               ------------ 
IP Address 172.2... Offline             cluster1-Other      IP Address
```

This example takes the resource named IP Address 172.24.11.0 offline, and releases the DHCP lease for that resource.

## PARAMETERS

### -Cluster
Specifies the name of the cluster on which to run this cmdlet.
If the input for this parameter is `.` or it is omitted, then the cmdlet runs on the local cluster.

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
Position: 1
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

## INPUTS

### Microsoft.FailoverClusters.PowerShell.ClusterResource

## OUTPUTS

### Microsoft.FailoverClusters.PowerShell.ClusterResource

## NOTES

## RELATED LINKS

[Where-Object](https://go.microsoft.com/fwlink/?LinkID=113423)

[Get-ClusterResource](./Get-ClusterResource.md)

[Update-ClusterNetworkNameResource](./Update-ClusterNetworkNameResource.md)

