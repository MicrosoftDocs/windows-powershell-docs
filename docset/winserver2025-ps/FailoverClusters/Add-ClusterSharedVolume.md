---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.FailoverClusters.PowerShell.dll-Help.xml
Module Name: FailoverClusters
ms.date: 11/22/2022
online version: https://learn.microsoft.com/powershell/module/failoverclusters/add-clustersharedvolume?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-ClusterSharedVolume
---

# Add-ClusterSharedVolume

## SYNOPSIS
Makes a volume available in Cluster Shared Volumes in a failover cluster.

## SYNTAX

```
Add-ClusterSharedVolume [[-Name] <StringCollection>] [-InputObject <PSObject>] [-Cluster <String>]
 [<CommonParameters>]
```

## DESCRIPTION

The `Add-ClusterSharedVolume` cmdlet makes a volume available in the Cluster Shared Volumes in a
failover cluster. The Cluster Shared Volume must be chosen from the disks in Available Storage (that
is, disks that have been added to the cluster but not assigned to a specific use in the cluster).

## EXAMPLES

### Example 1

```powershell
Add-ClusterSharedVolume -Name "Cluster Disk 4"
```

This example adds `Cluster Disk 4` to the Cluster Shared Volumes on the local cluster.

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

### -InputObject

Specifies the cluster disk resource to be added to the Cluster Shared Volumes.

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

Specifies the name of the cluster disk resource to add.

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

### Microsoft.FailoverClusters.PowerShell.ClusterResource

## OUTPUTS

### Microsoft.FailoverClusters.PowerShell.ClusterSharedVolume

## NOTES

## RELATED LINKS

[Add-ClusterDisk](./Add-ClusterDisk.md)

[Get-ClusterSharedVolume](./Get-ClusterSharedVolume.md)

[Move-ClusterSharedVolume](./Move-ClusterSharedVolume.md)

[Remove-ClusterSharedVolume](./Remove-ClusterSharedVolume.md)
