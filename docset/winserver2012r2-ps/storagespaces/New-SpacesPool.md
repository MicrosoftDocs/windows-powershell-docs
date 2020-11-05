---
external help file: StorSpaces2_Cmdlets.xml
online version: 
schema: 2.0.0
title: New-SpacesPool
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 7A0531FC-C604-4CC2-B8F5-29C794260507
ms.author: v-kaunu
ms.reviewer: brianlic
---

# New-SpacesPool

## SYNOPSIS
Creates a storage pool on the Storage Spaces subsystem.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
New-SpacesPool [-FriendlyName] <String> [-NumberOfPhysicalDisksToUse] <Int32>
 [[-NumberOfHotsparesToUse] <Int32>]
```

### UNNAMED_PARAMETER_SET_2
```
New-SpacesPool [-FriendlyName] <String> [-PhysicalDisks] <Object[]> [[-NumberOfHotsparesToUse] <Int32>]
```

## DESCRIPTION
The New-SpacesPool cmdlet creates a storage pool on the Storage Spaces subsystem with three or more eligible physical disks.
The storage pool can then be used to create storage spaces.

## EXAMPLES

### Example 1 - Create a storage pool with five physical disks
```
PS C:\>New-SpacesPool -FriendlyName MyPool -NumberOfPhysicalDisksToUse 5
```

This example creates a storage pool named MyPool using five available physical disks from the Available Disks (primordial) storage pool.

### Example 2 - Create a storage pool with an array of PhysicalDisk objects
```
PS C:\>New-SpacesPool -FriendlyName MyPool -PhysicalDisks $DiskArray
```

This example creates a storage pool named MyPool using the specified array of PhysicalDisk objects.

### Example 3 - Create a storage pool with two hot spares
```
PS C:\>New-SpacesPool -FriendlyName MyPool -NumberOfPhysicalDisksToUse 8 -NumberOfHotsparesToUse 2
```

This example creates a storage pool named MyPool using eight physical disks and assigns two physical disks to the pool for use as hot-spares in the event of a physical disk failure.

## PARAMETERS

### -FriendlyName
Specifies the friendly name of the storage pool to create.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NumberOfHotsparesToUse
Specifies how many physical disks to designate as hot spares, which are available to automatically replace failed disks.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NumberOfPhysicalDisksToUse
Specifies how many physical disks to use to create the storage pool.

```yaml
Type: Int32
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PhysicalDisks
Specifies the PhysicalDisk objects to use to create the storage pool.

```yaml
Type: Object[]
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByValue, ByPropertyName)
Accept wildcard characters: False
```

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_PhysicalDisk
You can pipe an array of PhysicalDisk objects to the **PhysicalDisks** parameter.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/microsoft/windows/storage/MSFT_StoragePool
This cmdlet outputs a StoragePool object.

## NOTES

## RELATED LINKS

