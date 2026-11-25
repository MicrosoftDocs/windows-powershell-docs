---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.FailoverClusters.PowerShell.dll-Help.xml
Module Name: FailoverClusters
ms.date: 10/21/2022
online version: https://learn.microsoft.com/powershell/module/failoverclusters/set-clusterresourcedependency?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-ClusterResourceDependency
---

# Set-ClusterResourceDependency

## SYNOPSIS
Specifies the resources that a particular resource depends on within a failover cluster.

## SYNTAX

```
Set-ClusterResourceDependency [[-Resource] <String>] [[-Dependency] <String>]
 [-InputObject <PSObject>] [-Cluster <String>] [<CommonParameters>]
```

## DESCRIPTION

The `Set-ClusterResourceDependency` cmdlet specifies the resources that a particular resource
depends on within a failover cluster. Existing dependencies will be overwritten by the dependencies
that you specify.

The term or can be used in the expression describing the dependency. For example, an or dependency
can be set up where a Network Name resource is dependent on either of two IP address resources,
instead of being dependent on both. This use of or dependencies is common in multi-site cluster
deployments.

## EXAMPLES

### Example 1

```powershell
Set-ClusterResourceDependency -Resource cluster1FS12 -Dependency "[IP Address 151.56.48.0]"
```

This example makes the resource called cluster1FS12 dependent on `[IP Address 151.56.48.0]`.

### Example 2

```powershell
$parameters = @{
    Resource = 'cluster1FS12'
    Dependency = '[IP Address 151.56.48.0] or [New IP Address]'
}
Set-ClusterResourceDependency @parameters
```

This example makes the resource called `cluster1FS12` dependent on either `[IP Address 151.56.48.0]`
or `[New IP Address]`.

This example uses splatting to pass parameter values from the `$Parameters` variable to the command.
Learn more about [Splatting](/powershell/module/microsoft.powershell.core/about/about_splatting).

### Example 3

```powershell
Set-ClusterResourceDependency -Resource cluster1FS12 -Dependency ""
```

This example clears the dependency list for the resource named `cluster1FS12`, so that it no longer
depends on any other resources.

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

### -Dependency

Specifies the dependency expression to set for this resource. The format for this is string is as
follows. `"[Resource Name 1] [and|or [Resource Name 2] [...] ]"Resource Name 1Resource Name 2`

 Resource names should be enclosed in square brackets as `[Cluster Disk 2]Cluster Disk 2`. To reset
 the resource dependency, use an empty string `""` in this parameter.

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

### -InputObject

Specifies the cluster resource for which to set the dependency expression.

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

Specifies the name of the cluster resource for which to set the dependency expression.

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

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.FailoverClusters.PowerShell.ClusterResource

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Add-ClusterResourceDependency](./Add-ClusterResourceDependency.md)

[Get-ClusterResourceDependency](./Get-ClusterResourceDependency.md)

[Get-ClusterResourceDependencyReport](./Get-ClusterResourceDependencyReport.md)

[Remove-ClusterResourceDependency](./Remove-ClusterResourceDependency.md)
