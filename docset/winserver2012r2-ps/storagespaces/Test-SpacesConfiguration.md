---
author: Kateyanne
description: 
external help file: StorSpaces2_Cmdlets.xml
manager: jasgro
Module Name: StorageSpaces
ms.author: v-kaunu
ms.date: 10/30/2017
ms.prod: powershell
ms.reviewer: brianlic
ms.topic: reference
online version: https://docs.microsoft.com/powershell/module/storagespaces/test-spacesconfiguration?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Test-SpacesConfiguration
---

# Test-SpacesConfiguration

## SYNOPSIS
Tests for unhealthy resources associated with a Storage Spaces storage pool.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Test-SpacesConfiguration [-StoragePool] <CimInstance> [-Passthru]
```

### UNNAMED_PARAMETER_SET_2
```
Test-SpacesConfiguration [-StoragePoolFriendlyName] <String> [-Passthru]
```

## DESCRIPTION
The Test-SpacesConfiguration cmdlet tests for unhealthy Storage Spaces resources.
It performs the following operations, and returns a **True** code if Storage Spaces is healthy:

Enumerate storage pools that unhealthy

Enumerate storage spaces that are unhealthy

Enumerate physical disks that are unhealthy

## EXAMPLES

### Example 1 - Test a storage pool
```
PS C:\>Test-SpacesConfiguration -StoragePoolFriendlyName Internal
This Storage Pool, the Storage Spaces created from this pool, and the Physical Disks in the Storage Pool are all currently healthy. 
True
```

This example tests a storage pool.

### Example 2 - Test a storage pool with verbose output
```
PS C:\>Test-SpacesConfiguration -StoragePoolFriendlyName Internal -Verbose
```

This example tests a storage pool and specifies for verbose output.

## PARAMETERS

### -Passthru
Specifies that if the storage pool is unhealthy, the cmdlet should output an object that represents the unhealthy pool.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StoragePool
Specifies the StoragePool object to test.

```yaml
Type: CimInstance
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StoragePoolFriendlyName
Specifies the friendly name of the storage pool to test.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_StoragePool
You can pipe a StoragePool object to the **StoragePool** parameter.

## OUTPUTS

### System.Boolean
This cmdlet outputs a Boolean object that represents whether Storage Spaces is healthy (**True**) or unhealthy (**False**).

### System.Object
If you specify the **Passthru** parameter and the storage pool is unhealthy, this cmdlet outputs an object that represents the unhealthy storage pool.

## NOTES

## RELATED LINKS

