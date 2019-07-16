---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-anbarr
author: andreabarr
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
title: Disable-PhysicalDiskIdentification
ms.reviewer:
ms.assetid: 92B5AA02-CA2C-43BA-A750-CBD0154E740E
---

# Disable-PhysicalDiskIdentification

## SYNOPSIS
Turns off the identification LED on the specified physical disk.

## SYNTAX

### ByName (Default)
```
Disable-PhysicalDiskIdentification [-FriendlyName] <String> [-CimSession <CimSession>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

### ByUniqueId
```
Disable-PhysicalDiskIdentification -UniqueId <String> [-CimSession <CimSession>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

### ByInputObject
```
Disable-PhysicalDiskIdentification -InputObject <CimInstance[]> [-CimSession <CimSession>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Disable-PhysicalDiskIndication** cmdlet turns off the identification LED on the specified physical disk.
The LED is typically used for visual identification of the location of a physical disk in an enclosure for removal and replacement operations.
This cmdlet requires a storage enclosure that supports SCSI Enclosure Services (SES).

## EXAMPLES

### Example 1: Disable the identification LED on all physical disks in a pool
```
PS C:\>$StPool = (Get-StoragePool -FriendlyName "SpacePool")
PS C:\> Disable-PhysicalDiskIndication -StoragePool $StPool
```

The first command gets the storage poll named SpacePool by using the Get-StoragePool cmdlet.
The command stores the pool in the $StPool variable.

The second command disables the identification LED on all physical disks associated with the storage pool in $StPool.

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
Specifies the friendly name of the disk on which to turn off the identification LED.

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
Specifies the UniqueID of the disk on which to turn off the identification LED.

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

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-StoragePool](./Get-StoragePool.md)

[Enable-PhysicalDiskIdentification](./Enable-PhysicalDiskIdentification.md)

