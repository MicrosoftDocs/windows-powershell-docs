---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.FailoverClusters.PowerShell.dll-Help.xml
Module Name: FailoverClusters
ms.date: 10/21/2022
online version: https://learn.microsoft.com/powershell/module/failoverclusters/remove-clusterresourcedependency?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-ClusterResourceDependency
---

# Remove-ClusterResourceDependency

## SYNOPSIS
Removes a dependency between two resources in a clustered role within a failover cluster.

## SYNTAX

```
Remove-ClusterResourceDependency [[-Resource] <String>] [[-Provider] <String>]
 [-InputObject <PSObject>] [-Cluster <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

The `Remove-ClusterResourceDependency` cmdlet removes a dependency between two resources in a
clustered role within a failover cluster.

A dependent resource is brought online after the resources on which it depends. Likewise, a
dependent resource is taken offline before the resources on which it depends. If no dependency is
configured between clustered resources, then the order in which they are brought online or taken
offline might vary.

## EXAMPLES

### Example 1

```powershell
$parameters = @{
    Resource = 'cluster1FS'
    Provider = 'IP Address 2001:4898:9:2:: (3)'
}
Remove-ClusterResourceDependency @parameters
```

This example removes the dependency between cluster resource `cluster1FS` and the resource named
`IP Address 2001:4898:9:2:: (3)`.

### Example 2

```powershell
$parameters = @{
    Provider = 'IP Address 2001:4898:9:2:: (3)'
}
Get-ClusterResource -Name cluster1FS | Remove-ClusterResourceDependency @parameters
```

This example removes the dependency between the cluster resource named `cluster1FS` and the resource
named `IP Address 2001:4898:9:2:: (3)`. This example uses splatting to pass parameter values from
the `$Parameters` variable to the command. Learn more about
[Splatting](/powershell/module/microsoft.powershell.core/about/about_splatting).

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

### -Confirm

Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

Specifies the cluster resource from which to remove the dependency.

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

Specifies the cluster resource on which to remove a dependency.

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

### -Resource

Specifies the name of the cluster resource from which to remove the dependency.

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

### -WhatIf

Shows what would happen if the cmdlet runs. The cmdlet isn't run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
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

[Add-ClusterResourceDependency](./Add-ClusterResourceDependency.md)

[Get-ClusterResourceDependency](./Get-ClusterResourceDependency.md)

[Set-ClusterResourceDependency](./Set-ClusterResourceDependency.md)
