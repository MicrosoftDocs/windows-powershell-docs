---
external help file: StorSpaces2_Cmdlets.xml
online version: 
schema: 2.0.0
title: Resize-SpacesVolume
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: DF376C09-7696-4789-84C0-3AFAC57CB453
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Resize-SpacesVolume

## SYNOPSIS
Resizes storage spaces and file system volumes.

## SYNTAX

```
Resize-SpacesVolume [-SpaceFriendlyName] <String> [-NewSize] <String> [[-StoragePoolFriendlyName] <String>]
 [-Confirm] [-WhatIf]
```

## DESCRIPTION
The Resize-SpacesVolume cmdlet extends a storage space and the file system volumes on it.
Shrinking the size of a storage space is not allowed, although this cmdlet does not check the input new size.
It only works with Microsoft System Reserved (MSR) partitions and a single primary partition.

## EXAMPLES

### Example 1 - Resize a storage space
```
PS C:\>Resize-SpacesVolume -SpaceFriendlyName "2ndSpace" -StoragePoolFriendlyName "2ndPool" -NewSize (2TB)
```

This example resizes a storage space named 2ndSpace on a storage pool named 2ndPool to 2TB.

## PARAMETERS

### -NewSize
Specifies the new size of the storage space and volume.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SpaceFriendlyName
Specifies the friendly name of the storage space to resize.

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

### -StoragePoolFriendlyName
Specifies the friendly name of the storage pool.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

### None

## OUTPUTS

### System.Object
This cmdlet outputs an object that represents the volume that was resized.

## NOTES

## RELATED LINKS

