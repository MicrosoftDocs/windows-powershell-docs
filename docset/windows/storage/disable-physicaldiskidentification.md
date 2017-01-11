---
author: brianlic
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
title: Disable-PhysicalDiskIdentification
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
{{Fill AsJob Description}}

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
{{Fill InputObject Description}}

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-StoragePool](./Get-StoragePool.md)

[Enable-PhysicalDiskIdentification](./Enable-PhysicalDiskIdentification.md)

