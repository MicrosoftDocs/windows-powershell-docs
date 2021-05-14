---
external help file: Failoverv2_Cmdlets.xml
Module Name: FailoverClusters
online version: https://docs.microsoft.com/powershell/module/failoverclusters/add-clusterresourcedependency?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Add-ClusterResourceDependency

## SYNOPSIS
Adds a resource to the list of resources on which a particular resource depends, using AND as the connector, within a failover cluster.

## SYNTAX

```
Add-ClusterResourceDependency [[-Resource] <String>] [[-Provider] <String>] [-Cluster <String>]
 [-InputObject <PSObject>]
```

## DESCRIPTION
The **Add-ClusterResourceDependency** cmdlet adds a resource to the list of resources on which a particular resource depends, using AND as the connector, within a failover cluster. Existing dependencies will remain on the list. If you specify the *InputObject* parameter, the *Resource* parameter will be ignored.

A dependent resource is brought online after the resources on which it depends.
A dependent resource is taken offline before the resources on which it depends.

## EXAMPLES

### Example 1
```
PS C:\> Add-ClusterResourceDependency -Resource "FileServer-(cluster1FS12)" -Provider "Cluster Disk 4"
Name                State               Group               ResourceType 
----                -----               -----               ------------ 
FileServer-(clus... Online              cluster1FS12        File Server
```

This example adds the resource named "Cluster Disk 4" to the list of resources on which the resource called "FileServer-(cluster1FS12)" depends, using AND as the connector.

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
Specifies the cluster resource for which to add the dependency.

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

### -Provider
Specifies the cluster resource to add as a dependency.

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

### -Resource
Specifies the name of the cluster resource for which to add the dependency.

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

## INPUTS

### Microsoft.FailoverClusters.PowerShell.ClusterResource

## OUTPUTS

### Microsoft.FailoverClusters.PowerShell.ClusterResource

## NOTES

## RELATED LINKS

[Get-ClusterResourceDependency](./Get-ClusterResourceDependency.md)

[Get-ClusterResourceDependencyReport](./Get-ClusterResourceDependencyReport.md)

[Remove-ClusterResourceDependency](./Remove-ClusterResourceDependency.md)

[Set-ClusterResourceDependency](./Set-ClusterResourceDependency.md)
