---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.FailoverClusters.PowerShell.dll-Help.xml
Module Name: FailoverClusters
ms.date: 11/22/2022
online version: https://learn.microsoft.com/powershell/module/failoverclusters/get-clustercheckpoint?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ClusterCheckpoint
---

# Get-ClusterCheckpoint

## SYNOPSIS
Retrieves a cryptographic key checkpoint or registry checkpoint for a resource.

## SYNTAX

```
Get-ClusterCheckpoint [[-ResourceName] <StringCollection>] [-CheckpointName <String>]
 [-RegistryCheckpoint] [-CryptoCheckpoint] [-InputObject <PSObject>] [-Cluster <String>]
 [<CommonParameters>]
```

## DESCRIPTION

The `Get-ClusterCheckpoint` cmdlet retrieves a cryptographic key checkpoint or registry checkpoint
for a resource.

Checkpoints help provide failover support for applications that store configuration information
locally instead of or in addition to storing information in the cluster configuration database.
Applications might store information locally in two ways. One way is to store configuration
information in the registry on the local server; another way is to use cryptographic keys on the
local server.

## EXAMPLES

### Example 1

```powershell
Get-ClusterCheckpoint
```

This example retrieves all cluster checkpoints.

### Example 2

```powershell
Get-ClusterResource -ResourceName "Cluster Name" | Get-ClusterCheckpoint -CryptoCheckpoint
```

This example retrieves the cryptographic checkpoints for the resource named `Cluster Name`.

## PARAMETERS

### -CheckpointName

Specifies the name of checkpoints for which to search. Use of wildcard expressions is accepted.

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

### -CryptoCheckpoint

Specifies that cryptographic checkpoints will be retrieved.

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

Specifies the cluster on which to run the cmdlet or the cluster resource for which to retrieve the
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

Specifies that registry checkpoints will be retrieved.

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

Specifies the resource for which to retrieve the checkpoint.

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

[Remove-ClusterCheckpoint](./Remove-ClusterCheckpoint.md)
