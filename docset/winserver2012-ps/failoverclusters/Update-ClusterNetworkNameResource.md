---
external help file: Failoverv2_Cmdlets.xml
online version: 
schema: 2.0.0
ms.assetid: 6B45F79C-1AAE-423B-A522-1FD8FD3B05B1
manager: dansimp
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Update-ClusterNetworkNameResource

## SYNOPSIS
Registers existing Network Name resources with a DNS server in a way that does not interrupt cluster availability.

## SYNTAX

```
Update-ClusterNetworkNameResource [[-Name] <StringCollection>] [-Cluster <String>] [-InputObject <PSObject>]
```

## DESCRIPTION
The **Update-ClusterNetworkNameResource** cmdlet registers existing Network Name resources with a DNS server in a way that does not interrupt cluster availability.

## EXAMPLES

### Example 1
```
PS C:\>Get-ClusterResource "Cluster Name" | Update-ClusterNetworkNameResource
Name                          State                         OwnerGroup                    ResourceType 
----                          -----                         ----------                    ------------ 
Cluster Name                  Online                        Cluster Group                 Network Name
```

This example registers the Network Name resources of the local cluster with a DNS server.

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
Specifies the network name resource to register with the DNS server.

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
Specifies the network name to be registered with the DNS server.

```yaml
Type: StringCollection
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
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

[Get-ClusterResource](./Get-ClusterResource.md)

[Update-ClusterIPResource](./Update-ClusterIPResource.md)

