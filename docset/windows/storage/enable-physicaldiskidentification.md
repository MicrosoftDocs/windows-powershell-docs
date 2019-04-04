---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: kenwith
author: kenwith
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: StorageScripts-help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Enable-PhysicalDiskIdentification
ms.reviewer:
ms.assetid: 0BA4723E-C564-429C-8F57-6B3A782F4813
---

# Enable-PhysicalDiskIdentification

## SYNOPSIS
Enables the identification LED on the specified physical disk.

## SYNTAX

### ByName (Default)
```
Enable-PhysicalDiskIdentification [-FriendlyName] <String> [-CimSession <CimSession>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

### ByUniqueId
```
Enable-PhysicalDiskIdentification -UniqueId <String> [-CimSession <CimSession>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

### ByInputObject
```
Enable-PhysicalDiskIdentification -InputObject <CimInstance[]> [-CimSession <CimSession>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Enable-PhysicalDiskIdentification** cmdlet enables the identification LED on the specified physical disk.
The LED is typically used for visual identification of the location of a physical disk in an enclosure for removal and replacement operations.
This cmdlet requires a storage enclosure that supports SCSI Enclosure Services (SES).

## EXAMPLES

### Example 1: Enable the identification LED on all physical disks in a pool
```
PS C:\>$stpool = (Get-StoragePool -FriendlyName "SpacePool")
PS C:\> Enable-PhysicalDiskIndication -StoragePool $stpool
```

This example enables the identification LED on all physical disks associated with the storage pool named SpacePool.
This is useful for identifying a specific virtual disk, when the LED on the disk in question is not functioning.

### Example 2: Enable the identification LED on all physical disks used by a virtual disk
```
PS C:\>$vdisk = (Get-VirtualDisk -FriendlyName "Bruce's Music")
PS C:\> Enable-PhysicalDiskIndication -VirtualDisk $vdisk
```

This example enables the identification LED on all physical disks associated with the virtual disk named Bruce's Music to visually identify the physical disk associated with the virtual disk.

### Example 3: Enable the identification LED on all disks that are not healthy
```
PS C:\>Get-PhysicalDisk | Where-Object -FilterScript { $_.HealthStatus -Ne "healthy" } | Enable-PhysicalDiskIndication
```

This example gets all physical disks with a health status that is not Healthy, and pipes the disks to the **Enable-PhysicalDiskIndication** cmdlet, enabling the LEDs on the disks, if supported by the drive enclosure.

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to complete.

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

### -CimSession

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

### -FriendlyName
Specifies the friendly name of the disk on which to enable the identification LED.

```yaml
Type: String
Parameter Sets: ByName
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -InputObject
Specifies the input object that is used in a pipeline command.

```yaml
Type: CimInstance[]
Parameter Sets: ByInputObject
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ThrottleLimit

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UniqueId
Specifies an ID used to uniquely identify a Disk object in the system.
The ID persists through restarts.

```yaml
Type: String
Parameter Sets: ByUniqueId
Aliases: Id

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_PhysicalDisk
You can pipe a **Disk** object to the *InputObject* parameter.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_PhysicalDisk
This cmdlet outputs an object that represents the physical disk for which you enabled the identification LED.

## NOTES
* The **Microsoft.Management.Infrastructure.CimInstance** object is a wrapper class that displays Windows Management Instrumentation (WMI) objects. The path after the pound sign (#) provides the namespace and class name for the underlying WMI object.

## RELATED LINKS

[Disable-PhysicalDiskIdentification](./Disable-PhysicalDiskIdentification.md)
