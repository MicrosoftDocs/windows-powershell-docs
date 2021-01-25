---
external help file: PhysicalDisk.cdxml-help.xml
Module Name: Storage
online version: 
schema: 2.0.0
title: Enable-PhysicalDiskIndication
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/29/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 53CD2A50-15FB-4ACE-991C-87F2E102E653
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Enable-PhysicalDiskIndication

## SYNOPSIS
Enables the identification LED on the specified physical disk.

## SYNTAX

### ByName (Default)
```
Enable-PhysicalDiskIndication [-FriendlyName] <String[]> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByUniqueId
```
Enable-PhysicalDiskIndication -UniqueId <String[]> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject (cdxml)
```
Enable-PhysicalDiskIndication -InputObject <CimInstance[]> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Enable-PhysicalDiskIndication** cmdlet enables the identification LED on the specified physical disk.
The LED is typically used for visual identification of the location of a physical disk in an enclosure for removal and replacement operations.
This cmdlet requires a storage enclosure that supports SCSI Enclosure Services (SES).

## EXAMPLES

### Example 1: Enable the identification LED on all physical disks in a pool
```
PS C:\> $stpool = (Get-StoragePool -FriendlyName "SpacePool")
PS C:\> Enable-PhysicalDiskIndication -StoragePool $stpool
```

This example enables the identification LED on all physical disks associated with the storage pool SpacePool.
This is useful for identifying a specific virtual disk, when the LED on the disk in question is not functioning.

### Example 2: Enable the identification LED on all physical disks used by a virtual disk
```
PS C:\> $vdisk = (Get-VirtualDisk -FriendlyName "Bruce's Music")
PS C:\> Enable-PhysicalDiskIndication -VirtualDisk $vdisk
```

This example enables the identification LED on all physical disks associated with the virtual disk named Bruce's Music to visually identify the physical disk associated with the virtual disk.

### Example 3: Enable the identification LED on all disks that are not healthy
```
PS C:\> Get-PhysicalDisk | Where-Object -FilterScript { $_.HealthStatus -Ne "healthy" } | Enable-PhysicalDiskIndication
```

This example gets all physical disks with a health status that is not Healthy, and pipes the disks to the **Enable-PhysicalDiskIndication** cmdlet, enabling the LEDs on the disks, if supported by the drive enclosure.

## PARAMETERS

### -AsJob
ps_cimcommon_asjob

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
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a New-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227967 or Get-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227966 cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: (All)
Aliases: Session

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -FriendlyName
Specifies the friendly name of the disk on which to enable the identification LED.

```yaml
Type: String[]
Parameter Sets: ByName
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InputObject
Specifies the Disk object on which to enable the LED.
Enter a Disk CIM object, which you can get using the Get-Disk cmdlet.

```yaml
Type: CimInstance[]
Parameter Sets: InputObject (cdxml)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -PassThru
Specifies that the cmdlet should output an object representing the physical disk for which you enabled the identification LED.
By default, this cmdlet does not generate any output.

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

### -ThrottleLimit
Specifies the maximum number of concurrent operations that can be established to run the cmdlet.
If this parameter is omitted or a value of `0` is entered, then Windows PowerShell® calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.
The throttle limit applies only to the current cmdlet, not to the session or to the computer.

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
Type: String[]
Parameter Sets: ByUniqueId
Aliases: Id

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_PhysicalDisk
You can pipe a Disk object to the **InputObject** parameter.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_PhysicalDisk
This cmdlet outputs an object that represents the physical disk for which you enabled the identification LED.

## NOTES

## RELATED LINKS

[Where-Object](https://go.microsoft.com/fwlink/?LinkID=113423)

[Disable-PhysicalDiskIndication](./Disable-PhysicalDiskIndication.md)

[Get-StoragePool](./Get-StoragePool.md)

[Get-VirtualDisk](./Get-VirtualDisk.md)

