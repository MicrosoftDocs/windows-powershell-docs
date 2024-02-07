---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.FailoverClusters.PowerShell.dll-Help.xml
Module Name: FailoverClusters
ms.date: 10/21/2022
online version: https://learn.microsoft.com/powershell/module/failoverclusters/remove-clustersharedvolume?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-ClusterSharedVolume
---

# Remove-ClusterSharedVolume

## SYNOPSIS
Removes a volume from the Cluster Shared Volumes in a failover cluster, and places it in Available
Storage in the cluster.

## SYNTAX

```
Remove-ClusterSharedVolume [[-Name] <StringCollection>] [-InputObject <PSObject>]
 [-Cluster <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

The `Remove-ClusterSharedVolume` cmdlet removes a volume from the Cluster Shared Volumes in a
failover cluster, and places it in Available Storage in the cluster. After placing a volume in
Available Storage, you can use the volume when you configure a new clustered role.

## EXAMPLES

### Example 1

```powershell
Remove-ClusterSharedVolume -Name "Cluster Disk 3"
```

This example removes the CSV named `Cluster Disk 3` from the Cluster Shared Volumes on the local
cluster, and places it in Available Storage.

### Example 2

```powershell
Get-ClusterSharedVolume -Name "Cluster Disk 4" | Remove-ClusterSharedVolume
```

This example removes the CSV named `Cluster Disk 4` from the Cluster Shared Volumes on the local
cluster, and places it in Available Storage.

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

Specifies the Cluster Shared Volume to remove.

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

Specifies the name of the Cluster Shared Volume to remove.

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

### Microsoft.FailoverClusters.PowerShell.ClusterSharedVolume

## OUTPUTS

### Microsoft.FailoverClusters.PowerShell.ClusterResource

## NOTES

## RELATED LINKS

[Add-ClusterSharedVolume](./Add-ClusterSharedVolume.md)

[Get-ClusterSharedVolume](./Get-ClusterSharedVolume.md)

[Move-ClusterSharedVolume](./Move-ClusterSharedVolume.md)
