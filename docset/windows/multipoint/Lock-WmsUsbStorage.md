---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-kaunu
author: Kateyanne
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MultiPoint.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: 
ms.topic: reference
online version: 
schema: 2.0.0
title: Lock-WmsUsbStorage
ms.reviewer:
ms.assetid: 7A39EF23-036C-4814-BEE9-E2A372996A67
---

# Lock-WmsUsbStorage

## SYNOPSIS
Prevents USB storage devices from being used.

## SYNTAX

### LockById
```
Lock-WmsUsbStorage [-StationId] <UInt32[]> [-Server <String>] [<CommonParameters>]
```

### LockAll
```
Lock-WmsUsbStorage [-All] [-Server <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Lock-WmsUsbStorage** cmdlet prevents the use of any station-attached USB storage devices.
If a device is already attached when you run **Lock-WmsUsbStorage**, they are logically removed.
Any USB devices that are subsequently added to a station are hidden.

## EXAMPLES

### Example 1: Lock USB storage devices
```
PS C:\> Lock-WmsUsbStorage -StationId 2
```

This command prevents the use of all USB storage devices on the specified station.

## PARAMETERS

### -All
Indicates that this operation applies to all sessions on the target host.

```yaml
Type: SwitchParameter
Parameter Sets: LockAll
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Server
Specifies the fully qualified host name of the MultiPoint Server that is the target of the command.
The default is localhost.

```yaml
Type: String
Parameter Sets: (All)
Aliases: ComputerName

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StationId
Specifies an array MultiPoint station IDs.
The acceptable values for this parameter are: 1 through the number of stations.

```yaml
Type: UInt32[]
Parameter Sets: LockById
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Unlock-WmsUsbStorage](./Unlock-WmsUsbStorage.md)

