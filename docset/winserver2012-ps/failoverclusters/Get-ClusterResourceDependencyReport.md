---
external help file: Failoverv2_Cmdlets.xml
Module Name: FailoverClusters
online version: https://learn.microsoft.com/powershell/module/failoverclusters/get-clusterresourcedependencyreport?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-ClusterResourceDependencyReport

## SYNOPSIS
Generates a report that lists the dependencies between resources in a failover cluster.

## SYNTAX

```
Get-ClusterResourceDependencyReport [-Cluster <String>] [-Group <String>] [-InputObject <PSObject>]
 [-Resource <String>]
```

## DESCRIPTION
The **Get-ClusterResourceDependencyReport** cmdlet generates a report that lists the dependencies between resources in a failover cluster.

The report has a filename extension of MHT.
For convenience in storing and finding the report, you can pipe this cmdlet to the Copy-Itemhttp://go.microsoft.com/fwlink/?LinkID=113292 cmdlet and specify a destination folder into which to copy the report.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-ClusterResourceDependencyReport -Group cluster1FS12
Mode                LastWriteTime     Length Name 
----                -------------     ------ ---- 
-a---        10/15/2008   6:29 PM      59299 fb509e66-8d02-4881-8184-6be5b1bfa4c2.mht
```

This example creates a dependency report file for the clustered file server, or resource group, named cluster1FS12 on the local cluster.

### EXAMPLE 2
```
PS C:\>Get-ClusterResourceDependencyReport -Group cluster1FS12 | Copy-Item -Destination C:\users\user1
```

This example creates a dependency report file for the clustered file server, or resource group, named cluster1FS12 on the local cluster.
The dependency report is copied to C:\users\user1.

### EXAMPLE 3
```
PS C:\>Get-ClusterGroup | Get-ClusterResourceDependencyReport | Copy-Item -Destination \\fileserver\share
```

This example creates a dependency report file for each clustered role, or resource group, on the local cluster, and copies all reports to \\\\fileserver\share.

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
Specifies the name of the cluster group for which to generate the dependency report.

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
Specifies the cluster group or cluster resource for which to create the dependency report.

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

### -Resource
Specifies the name of the cluster resource for which to generate the dependency report.

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

## INPUTS

### Microsoft.FailoverClusters.PowerShell.ClusterGroup

### Microsoft.FailoverClusters.PowerShell.ClusterResource

## OUTPUTS

### System.IO.FileInfo

## NOTES

## RELATED LINKS

[Copy-Item](https://go.microsoft.com/fwlink/?LinkID=113292)

[Add-ClusterResourceDependency](./Add-ClusterResourceDependency.md)

[Remove-ClusterResourceDependency](./Remove-ClusterResourceDependency.md)

[Set-ClusterResourceDependency](./Set-ClusterResourceDependency.md)

