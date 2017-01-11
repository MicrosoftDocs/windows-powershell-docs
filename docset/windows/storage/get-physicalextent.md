---
author: brianlic-msft
description: 
external help file: StorageScripts-help.xml
keywords: powershell, cmdlet
manager: alanth
ms.date: 2016-12-20
ms.prod: powershell
ms.technology: powershell
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-PhysicalExtent
ms.assetid: 65DD9798-9AF5-4E64-AA66-421AA98F8704
---

# Get-PhysicalExtent

## SYNOPSIS
Gets physical allocations for a physical disk, storage tier, or virtual disk.

## SYNTAX

### ByVirtualDisk
```
Get-PhysicalExtent -VirtualDisk <CimInstance> [-CimSession <CimSession>] [<CommonParameters>]
```

### ByStorageTier
```
Get-PhysicalExtent -StorageTier <CimInstance> [-CimSession <CimSession>] [<CommonParameters>]
```

### ByPhysicalDisk
```
Get-PhysicalExtent -PhysicalDisk <CimInstance> [-CimSession <CimSession>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-PhysicalExtent** cmdlet gets the physical allocations for a physical disk, storage tier, or virtual disk.

## EXAMPLES

### Example 1: Get all physical extents on a disk
```
PS C:\>Get-PhysicalExtent -PhysicalDisk (Get-PhysicalDisk -FriendlyName "PhysicalDisk4")
```

This command gets all physical extents on the physical disk named PhysicalDisk4.
The command uses **Get-PhysicalDisk** to obtain PhysicalDisk4.

## PARAMETERS

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a New-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227967 or Get-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227966 cmdlet.
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
To obtain a **PhysicalDisk** obje3t, use the Get-PhysicalDisk cmdlet.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

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

## RELATED LINKS

[Get-PhysicalDisk](./Get-PhysicalDisk.md)

[Get-PhysicalExtentAssociation](./Get-PhysicalExtentAssociation.md)

[Get-StorageTier](./Get-StorageTier.md)

[Get-VirtualDisk](./Get-VirtualDisk.md)

