---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.FailoverClusters.PowerShell.dll-Help.xml
Module Name: FailoverClusters
ms.date: 10/21/2022
online version: https://learn.microsoft.com/powershell/module/failoverclusters/remove-clusterresource?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-ClusterResource
---

# Remove-ClusterResource

## SYNOPSIS
Removes a clustered resource from the failover cluster.

## SYNTAX

```
Remove-ClusterResource [[-Name] <StringCollection>] [-Force] [-InputObject <PSObject>]
 [-Cluster <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

The `Remove-ClusterResource` cmdlet removes a clustered resource from the failover cluster. Before
removing a resource, be sure to review whether any other resource is dependent on that resource.

## EXAMPLES

### Example 1

```powershell
Remove-ClusterResource -Name "Cluster Disk 4"
```

This example prompts the user for confirmation and then deletes the cluster named `Cluster Disk 4`
from the local cluster.

### Example 2

```powershell
Remove-ClusterResource -Name "Cluster Disk 5" -Force
```

This example deletes the cluster named `Cluster Disk 5` from the local cluster without prompting for
confirmation.

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

### -Force

Runs the cmdlet without prompting for confirmation. By default the cmdlet will ask for confirmation
from the user before proceeding.

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

### -InputObject

Specifies the cluster resource to remove.

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

Specifies the name of the cluster resource to remove.

```yaml
Type: StringCollection
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

### None

## NOTES

## RELATED LINKS

[Add-ClusterResource](./Add-ClusterResource.md)

[Get-ClusterResource](./Get-ClusterResource.md)

[Move-ClusterResource](./Move-ClusterResource.md)

[Resume-ClusterResource](./Resume-ClusterResource.md)

[Start-ClusterResource](./Start-ClusterResource.md)

[Stop-ClusterResource](./Stop-ClusterResource.md)

[Suspend-ClusterResource](./Suspend-ClusterResource.md)
