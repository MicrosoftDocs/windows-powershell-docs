---
external help file: Failoverv2_Cmdlets.xml
Module Name: FailoverClusters
online version: https://learn.microsoft.com/powershell/module/failoverclusters/add-clusterresource?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Add-ClusterResource

## SYNOPSIS
Adds a resource to a clustered role, or resource group, in a failover cluster.

## SYNTAX

```
Add-ClusterResource [-Name] <String> [[-Group] <String>] [-ResourceType] <String> [-Cluster <String>]
 [-InputObject <PSObject>] [-SeparateMonitor]
```

## DESCRIPTION
The **Add-ClusterResource** cmdlet adds a resource to a clustered role, or resource group, in a failover cluster.
Before adding the resource, obtain the resource type and the name of the group to which to add the resource.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Add-ClusterResource -Name resource1 -ResourceType "IP Address" -Group ClusterSrv1
Name                State               Group               ResourceType 
----                -----               -----               ------------        
resource1           Offline             ClusterSrv1         IP Address
```

This example creates a new IP Address resource called resource1 on the local cluster.
The cmdlet configures the resource as part of the clustered role, or resource group, called ClusterSrv1.

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

### -Group
Specifies the name of the clustered role where the new resource is added.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Specifies the clustered role where the new resource is added.

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
Specifies the name of the cluster resource to create.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceType
Specifies the name of the cluster resource type for the new cluster resource.

```yaml
Type: String
Parameter Sets: (All)
Aliases: restype, type

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SeparateMonitor
Specifies that the new resource should run in a separate resource monitor.

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

### Microsoft.FailoverClusters.PowerShell.ClusterGroup

## OUTPUTS

### Microsoft.FailoverClusters.PowerShell.ClusterResource

## NOTES

## RELATED LINKS

[Get-ClusterResource](./Get-ClusterResource.md)

[Move-ClusterResource](./Move-ClusterResource.md)

[Remove-ClusterResource](./Remove-ClusterResource.md)

[Resume-ClusterResource](./Resume-ClusterResource.md)

[Start-ClusterResource](./Start-ClusterResource.md)

[Stop-ClusterResource](./Stop-ClusterResource.md)

[Suspend-ClusterResource](./Suspend-ClusterResource.md)

