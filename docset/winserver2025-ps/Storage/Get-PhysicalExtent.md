---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: StorageScripts-help.xml
Module Name: Storage
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/storage/get-physicalextent?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PhysicalExtent
---

# Get-PhysicalExtent

## SYNOPSIS
This cmdlet gets physical allocations for a physical disk, storage tier, or virtual disk. The "extent" (also known as "allocation" or "slab")  is the area on a pooled disk containing one fragment of data for storage space.

## SYNTAX

### ByVirtualDisk
```yaml
Get-PhysicalExtent -VirtualDisk <CimInstance> [-CimSession <CimSession>] [<CommonParameters>]
```

### ByStorageTier
```yaml
Get-PhysicalExtent -StorageTier <CimInstance> [-CimSession <CimSession>] [<CommonParameters>]
```

### ByPhysicalDisk
```yaml
Get-PhysicalExtent -PhysicalDisk <CimInstance> [-CimSession <CimSession>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-PhysicalExtent** cmdlet gets the physical allocations for a physical disk, storage tier, or virtual disk.

## EXAMPLES

### Example 1: Get physical extents on one specific physical disks
```Powershell
PS C:\>Get-PhysicalExtent -PhysicalDisk $(Get-PhysicalDisk)[0]
```
This command gets physical extents on all physical disks on the computer.

### Example 2: Get all physical extents on all physical disks

```Powershell
PS C:\>Get-PhysicalDisk | Get-PhysicalExtent
```

This command gets all physical extents on all physical disks on the computer.

### Example 3: Get extents on a specific disk
```Powershell
PS C:\>Get-PhysicalExtent -PhysicalDisk (Get-PhysicalDisk -FriendlyName "PhysicalDisk4")
```

This command gets all physical extents on the physical disk named PhysicalDisk4.
The command uses **Get-PhysicalDisk** to obtain PhysicalDisk4.

### Example 4: Get all physical extents on a disk (Other Version)
```Powershell
PS C:\>Get-PhysicalDisk -FriendlyName "PhysicalDisk4" | Get-PhysicalExtent
```

This command gets all physical extents on the physical disk named PhysicalDisk4, using PowerShell pipe.
The command uses **Get-PhysicalDisk** to obtain PhysicalDisk4.

## PARAMETERS

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PhysicalDisk
Specifies physical disk.
To obtain a **PhysicalDisk** object, use the Get-PhysicalDisk cmdlet.

```yaml
Type: CimInstance
Parameter Sets: ByPhysicalDisk
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -StorageTier
Specifies storage tier.
To obtain a **StorageTier** object, use the Get-StorageTier cmdlet.

```yaml
Type: CimInstance
Parameter Sets: ByStorageTier
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VirtualDisk
Specifies virtual disk.
To obtain a **VirtualDisk** object, use the Get-VirtualDisk cmdlet.

```yaml
Type: CimInstance
Parameter Sets: ByVirtualDisk
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_PhysicalDisk
You can pass a **PhysicalDisk** object to this cmdlet.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_StorageTier
You can pass a **StorageTier** object to this cmdlet.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_VirtualDisk
You can pass a **VirtualDisk** object to this cmdlet.

## OUTPUTS

### PhysicalExtent
This cmdlet returns the physical allocation that is associated with the input object.

## NOTES

* When used in Failover Cluster, cmdlets from the Storage module operate on cluster level (all servers in the cluster).

## RELATED LINKS

[Get-PhysicalDisk](./Get-PhysicalDisk.md)

[Get-PhysicalExtentAssociation](./Get-PhysicalExtentAssociation.md)

[Get-StorageTier](./Get-StorageTier.md)

[Get-VirtualDisk](./Get-VirtualDisk.md)

