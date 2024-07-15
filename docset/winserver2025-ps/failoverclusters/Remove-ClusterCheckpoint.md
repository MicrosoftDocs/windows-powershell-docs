---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.FailoverClusters.PowerShell.dll-Help.xml
Module Name: FailoverClusters
ms.date: 01/09/2023
online version: https://learn.microsoft.com/powershell/module/failoverclusters/remove-clustercheckpoint?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-ClusterCheckpoint
---

# Remove-ClusterCheckpoint

## SYNOPSIS
Removes a cryptographic key checkpoint or registry checkpoint for a resource.

## SYNTAX

```
Remove-ClusterCheckpoint [[-ResourceName] <String>] [-Force] [-CheckpointName <String>]
 [-RegistryCheckpoint] [-CryptoCheckpoint] [-InputObject <PSObject>] [-Cluster <String>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

The `Remove-ClusterCheckpoint` cmdlet removes a cryptographic key checkpoint or registry
checkpoint for a resource.

Checkpoints help provide failover support for applications that store configuration information
locally instead of or in addition to storing information in the cluster configuration database.
Applications might store information locally in two ways. One way is to store configuration
information in the registry on the local server; another way is to use cryptographic keys on the
local server.

## EXAMPLES

### Example 1

```powershell
$checkpoint = Get-ClusterCheckpoint -ResourceName "Cluster Name" -RegistryCheckpoint
$checkpoint | Remove-ClusterCheckpoint -Confirm:$false
```

This example returns all registry checkpoints for the resource named `Cluster Name`, then removes
them without user confirmation.

## PARAMETERS

### -CheckpointName

Specifies the name of the checkpoint to remove.

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

### -CryptoCheckpoint

Specifies that cryptographic key checkpoints will be removed.

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

Specifies the cluster on which to run the cmdlet or the cluster resource from which to remove the
checkpoint.

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

### -RegistryCheckpoint

Specifies that registry checkpoints will be removed.

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

### -ResourceName

Specifies the resource from which a checkpoint should be removed.

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

### Microsoft.FailoverClusters.PowerShell.Cluster

### Microsoft.FailoverClusters.PowerShell.ClusterResource

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Add-ClusterCheckpoint](./Add-ClusterCheckpoint.md)

[Get-ClusterCheckpoint](./Get-ClusterCheckpoint.md)
