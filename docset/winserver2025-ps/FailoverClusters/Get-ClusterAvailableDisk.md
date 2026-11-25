---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.FailoverClusters.PowerShell.dll-Help.xml
Module Name: FailoverClusters
ms.date: 11/22/2022
online version: https://learn.microsoft.com/powershell/module/failoverclusters/get-clusteravailabledisk?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ClusterAvailableDisk
---

# Get-ClusterAvailableDisk

## SYNOPSIS
Gets information about the disks that can support Failover Clustering and are visible to all nodes,
but aren't yet part of the set of clustered disks.

## SYNTAX

```
Get-ClusterAvailableDisk [[-Cluster] <String>] [-Disk <CimInstance>] [-All]
 [-InputObject <PSObject>] [<CommonParameters>]
```

## DESCRIPTION

The `Get-ClusterAvailableDisk` cmdlet gets information about the disks that can support Failover
Clustering and are visible to all nodes, but aren't yet part of the set of clustered disks.

If a disk is unexpectedly missing from the list of disks that are available for use in the cluster,
then make sure that the configuration of the storage allows the operating system on all clustered
servers to recognize and mount the disk as needed. The disk must be a basic disk, not a dynamic
disk, and shouldn't be exposed to any other servers.

## EXAMPLES

### Example 1

```powershell
Get-ClusterAvailableDisk
```

This example lists the disks that are ready to be added to the cluster.

### Example 2

```powershell
Get-ClusterAvailableDisk | Add-ClusterDisk
```

This example adds all disks that are ready to be added to the local cluster.

## PARAMETERS

### -All

{{Fill All Description}}

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

### -Cluster

Specifies the name of the cluster on which to run this cmdlet. If the input for this parameter is
`.` or it is omitted, then the cmdlet runs on the local cluster.

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

### -Disk

Specifies the disks on which to enumerate.

```yaml
Type: CimInstance
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -InputObject

Specifies the cluster on which to enumerate available shared disks.

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

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.FailoverClusters.PowerShell.Cluster

## OUTPUTS

### Microsoft.FailoverClusters.PowerShell.ClusterDiskInfo

## NOTES

## RELATED LINKS

[Add-ClusterDisk](./Add-ClusterDisk.md)
