---
external help file: StorSpaces2_Cmdlets.xml
online version: 
schema: 2.0.0
title: New-SpacesVolume
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 4BDC4BE1-9954-499E-985B-6C33C8A72B3D
ms.author: v-kaunu
ms.reviewer: brianlic
---

# New-SpacesVolume

## SYNOPSIS
Creates a storage space and then creates and formats a volume on the storage space.

## SYNTAX

```
New-SpacesVolume [-StoragePoolFriendlyName] <String> [-CreateClusterSharedVolume] [[-FileSystem] <String>]
 [-SpaceFriendlyName] <String> [-Size] <String> [-ResiliencyType] <String> [-ProvisioningType] <String>
 [[-DriveLetterToUse] <Char>] [-MaximumColumnCount] [[-InterleaveBytes] <UInt64>] [[-ClusterSize] <String>]
 [-Confirm] [-WhatIf]
```

## DESCRIPTION
The New-SpacesVolume cmdlet creates a storage space, initializes the new virtual disk (storage space), creates a partition on virtual disk, and then formats the volume.
It can also optionally create a Cluster Shared Volume (CSV) on the newly formatted volume when run on a failover cluster.

## EXAMPLES

### Example 1 - Create a thinly provisioned mirror space
```
PS C:\>New-SpacesVolume -StoragePoolFriendlyName Internal -SpaceFriendlyName Test -Size (5GB) -ResiliencyType Mirror -ProvisioningType Thin
```

This example creates a storage space named Test, which is a thinly provisioned mirror space, and then creates and formats a volume on the storage space.

### Example 2 - Create a thinly provisioned mirror space and assign a specific drive letter
```
PS C:\>New-SpacesVolume -StoragePoolFriendlyName Internal -SpaceFriendlyName Test -Size (5GB) -ResiliencyType Mirror -ProvisioningType Thin -DriveLetterToUse T -FileSystem NTFS
```

This example creates a storage space named Test, which is a thinly provisioned mirror space, and then creates and formats an NTFS volume on the storage space, and assigns drive letter T to the volume.

### Example 3 - Create a fixed mirror space and create a Cluster Shared Volume
```
PS C:\>New-SpacesVolume -StoragePoolFriendlyName Internal -SpaceFriendlyName Test -Size (5GB) -ResiliencyType Mirror -ProvisioningType Fixed -CSV
```

This example creates a 5GB mirror space, with fixed provisioning, and creates a Cluster Shared Volume (CSV) after creation. 
Note: Requires a clustered storage pool.

## PARAMETERS

### -ClusterSize
```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 9
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CreateClusterSharedVolume
Creates a CSV on the volume.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 10
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DriveLetterToUse
Specifies the drive letter to assign to the storage space.

```yaml
Type: Char
Parameter Sets: (All)
Aliases: 

Required: False
Position: 6
Default value: None
Accept pipeline input: True (ByValue, ByPropertyName)
Accept wildcard characters: False
```

### -FileSystem
Specifies the file system to use on the volume.
Acceptable values are **NTFS** and **ReFS**.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 11
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InterleaveBytes
```yaml
Type: UInt64
Parameter Sets: (All)
Aliases: 

Required: False
Position: 8
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaximumColumnCount
```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 7
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProvisioningType
Specifies whether to create a fixed or thinly provisioned storage space.
Acceptable values are **Fixed** or **Thin**.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 5
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResiliencyType
Specifies the resiliency setting to use.
Acceptable values are **Mirror**, **Parity**, and **Simple**, which does not include any resiliency.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Size
Specifies the size of the storage space.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SpaceFriendlyName
Specifies the friendly name of the storage space.

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

### -StoragePoolFriendlyName
Specifies the friendly name of the storage pool on which to create the storage space.

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
This cmdlet returns an object that contains information about the storage space and the volume hosted on the storage space.

## NOTES

## RELATED LINKS

