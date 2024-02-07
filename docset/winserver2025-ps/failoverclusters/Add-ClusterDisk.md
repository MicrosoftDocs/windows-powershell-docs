---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.FailoverClusters.PowerShell.dll-Help.xml
Module Name: FailoverClusters
ms.date: 11/22/2022
online version: https://learn.microsoft.com/powershell/module/failoverclusters/add-clusterdisk?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-ClusterDisk
---

# Add-ClusterDisk

## SYNOPSIS
Makes a new disk available for use in a failover cluster.

## SYNTAX

```
Add-ClusterDisk [-InputObject] <PSObject[]> [-Cluster <String>] [<CommonParameters>]
```

## DESCRIPTION

The `Add-ClusterDisk` cmdlet makes a new disk available for use in a failover cluster. The disk
(LUN) must be exposed to all nodes in the failover cluster, and shouldn't be exposed to any other
servers.

When adding a disk, make sure that the configuration of the storage allows the operating system to
recognize and mount the disk as needed. The disk must be a basic disk, not a dynamic disk, and
shouldn't be exposed to servers outside the cluster. The `Get-ClusterAvailableDisk` cmdlet gets
information about disks that you can add to the cluster.

## EXAMPLES

### Example 1: Add available disks to the Available Storage group

```powershell
Get-ClusterAvailableDisk | Add-ClusterDisk
```

This example identifies the disks that are ready to be added to the cluster, and then adds them to
Available Storage cluster group.

### Example 2: Add a specific available disk to Available Storage

```powershell
Get-ClusterAvailableDisk | Where-Object -FilterScript { $_.ScsiAddress -Eq 50331651 } | Add-ClusterDisk
```

This example examines disks that are ready to be added to the cluster, finds the disk with a
specific SCSI address, and adds it to Available Storage cluster group.

### Example 3: Cluster a physical disk

```powershell
Get-Disk -Number 11 | Add-ClusterDisk
```

This example clusters a physical disk. This cmdlet adds a physical disk to the cluster
_Available Storage_.

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

Specifies the list of shared disks to add to the cluster. The list of disks is generated with the
`Get-ClusterAvailableDisk` cmdlet.

```yaml
Type: PSObject[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
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

### Microsoft.FailoverClusters.PowerShell.ClusterDiskInfo

### Microsoft.Management.Infrastructure.CimInstance

This object is output from the `Get-Disk` and the `Get-VirtualDisk` cmdlets.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_Disk

The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays
Windows Management Instrumentation (WMI) objects. The path after the pound sign (`#`) provides the
namespace and class name for the underlying WMI object.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_VirtualDisk

The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays
Windows Management Instrumentation (WMI) objects. The path after the pound sign (`#`) provides the
namespace and class name for the underlying WMI object.

## OUTPUTS

### Microsoft.FailoverClusters.PowerShell.ClusterResource

## NOTES

## RELATED LINKS

[Get-ClusterAvailableDisk](./Get-ClusterAvailableDisk.md)

[Test-Cluster](./Test-Cluster.md)

[Get-Disk](../storage/Get-Disk.md)

[Get-VirtualDisk](../storage/Get-VirtualDisk.md)
