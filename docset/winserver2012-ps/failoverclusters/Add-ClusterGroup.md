---
external help file: Failoverv2_Cmdlets.xml
Module Name: FailoverClusters
online version: https://docs.microsoft.com/powershell/module/failoverclusters/add-clustergroup?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Add-ClusterGroup

## SYNOPSIS
Adds an empty resource group to the failover cluster configuration, in preparation for adding clustered resources to the group.

## SYNTAX

```
Add-ClusterGroup [-Name] <StringCollection> [-Cluster <String>] [-InputObject <PSObject>]
```

## DESCRIPTION
The **Add-ClusterGroup** cmdlet adds an empty resource group to the failover cluster configuration, in preparation for adding clustered resources to the group.
A resource group, or a clustered role, is the unit of failover.
During failover, all resources in the resource group move together.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Add-ClusterGroup -Name Group1
Name                       OwnerNode                                      State 
----                       ---------                                      ----- 
Group1                     node1                                         Online
```

This example adds an empty resource group called Group1 to the failover cluster.

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
Specifies the cluster on which to create the resource group.

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
Specifies the name of the resource group to add.

```yaml
Type: StringCollection
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

### Microsoft.FailoverClusters.PowerShell.Cluster

## OUTPUTS

### Microsoft.FailoverClusters.PowerShell.ClusterGroup

## NOTES

## RELATED LINKS

[Get-ClusterGroup](./Get-ClusterGroup.md)

[Move-ClusterGroup](./Move-ClusterGroup.md)

[Remove-ClusterGroup](./Remove-ClusterGroup.md)

[Start-ClusterGroup](./Start-ClusterGroup.md)

[Stop-ClusterGroup](./Stop-ClusterGroup.md)

