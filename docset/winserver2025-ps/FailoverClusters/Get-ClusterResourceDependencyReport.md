---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.FailoverClusters.PowerShell.dll-Help.xml
Module Name: FailoverClusters
ms.date: 11/22/2022
online version: https://learn.microsoft.com/powershell/module/failoverclusters/get-clusterresourcedependencyreport?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ClusterResourceDependencyReport
---

# Get-ClusterResourceDependencyReport

## SYNOPSIS
Generates a report that lists the dependencies between resources in a failover cluster.

## SYNTAX

```
Get-ClusterResourceDependencyReport [-Resource <String>] [-Group <String>] [-InputObject <PSObject>]
 [-Cluster <String>] [<CommonParameters>]
```

## DESCRIPTION

The `Get-ClusterResourceDependencyReport` cmdlet generates a report that lists the dependencies
between resources in a failover cluster.

The report has a filename extension of MHT. For convenience in storing and finding the report, you
can pipe this cmdlet to the [Copy-Item](https://go.microsoft.com/fwlink/?LinkID=113292) cmdlet and
specify a destination folder into which to copy the report.

## EXAMPLES

### Example 1

```powershell
Get-ClusterResourceDependencyReport -Group cluster1FS12
```

This example creates a dependency report file for the clustered file server, or resource group,
named `cluster1FS12` on the local cluster.

### Example 2

```powershell
Get-ClusterResourceDependencyReport -Group cluster1FS12 | Copy-Item -Destination C:\users\user1
```

This example creates a dependency report file for the clustered file server, or resource group,
named `cluster1FS12` on the local cluster. The dependency report is copied to `C:\users\user1`.

### Example 3

```powershell
Get-ClusterGroup | Get-ClusterResourceDependencyReport | Copy-Item -Destination \\fileserver\share
```

This example creates a dependency report file for each clustered role, or resource group, on the
local cluster, and copies all reports to `\\fileserver\share`.

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

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

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
