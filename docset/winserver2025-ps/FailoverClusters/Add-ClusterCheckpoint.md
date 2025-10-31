---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.FailoverClusters.PowerShell.dll-Help.xml
Module Name: FailoverClusters
ms.date: 11/22/2022
online version: https://learn.microsoft.com/powershell/module/failoverclusters/add-clustercheckpoint?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-ClusterCheckpoint
---

# Add-ClusterCheckpoint

## SYNOPSIS
Adds a cryptographic key checkpoint or registry checkpoint for a resource.

## SYNTAX

```
Add-ClusterCheckpoint [[-ResourceName] <String>] [-CryptoCheckpointName <String>]
 [-CryptoCheckpointType <String>] [-CryptoCheckpointKey <String>] [-RegistryCheckpoint <String>]
 [-InputObject <PSObject>] [-Cluster <String>] [<CommonParameters>]
```

## DESCRIPTION

The `Add-ClusterCheckpoint` cmdlet adds a cryptographic key checkpoint or registry checkpoint for
a resource.

Checkpoints help provide failover support for applications that store configuration information
locally instead of or in addition to storing information in the cluster configuration database.
Applications might store information locally in two ways. One way is to store configuration
information in the registry on the local server; another way is to use cryptographic keys on the
local server.

## EXAMPLES

### Example 1: Add registry checkpoint

```powershell
Add-ClusterCheckpoint -ResourceName "Cluster Name" -RegistryCheckpoint "software\clusname"
```

This example adds a registry checkpoint called `software\clusname` for the resource named cluster
name.

### Example 2: Add cryptographic checkpoint

```powershell
$parameters = @{
    CryptoCheckpointName = 'Microsoft Base Cryptographic Provider v1.0'
    CryptoCheckpointType = '1'
    CryptoCheckpointKey = 'Crypto'
}
Get-ClusterResource -Name "Cluster Name" | Add-ClusterCheckpoint @parameters
```

This example adds a cryptographic checkpoint for the resource named Cluster Name. This example uses
splatting to pass parameter values from the `$Parameters` variable to the command. Learn more about
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

### -CryptoCheckpointKey

Specifies the key of a cryptographic key checkpoint to add.

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

### -CryptoCheckpointName

Specifies the name of a cryptographic key checkpoint to add.

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

### -CryptoCheckpointType

Specifies the type of a cryptographic key checkpoint to add. Options depend on the cryptographic
provider.

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

Specifies the cluster on which to run the cmdlet or the cluster resource for which the checkpoint
should be added.

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

Specifies the name of the registry checkpoint to add.

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

### -ResourceName

Specifies the resource for which a checkpoint should be added.

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

### Microsoft.FailoverClusters.PowerShell.Cluster

### Microsoft.FailoverClusters.PowerShell.ClusterResource

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Get-ClusterCheckpoint](./Get-ClusterCheckpoint.md)

[Get-ClusterResource](./Get-ClusterResource.md)

[Remove-ClusterCheckpoint](./Remove-ClusterCheckpoint.md)
