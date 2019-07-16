---
external help file: Microsoft.HyperV.PowerShell.dll-Help.xml
Module Name: Hyper-V
online version: 
schema: 2.0.0
title: Get-VMStoragePath
ms.author: v-anbarr
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: andreabarr
manager: jasgro
ms.date: 2017-10-30
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 64CF28D6-1FE4-4FF1-8F64-1C3946E0F2B3
---

# Get-VMStoragePath

## SYNOPSIS
Gets the storage paths in a storage resource pool.

## SYNTAX

```
Get-VMStoragePath [[-Path] <String[]>] [-ResourcePoolName] <String[]> [-ResourcePoolType] <VMResourcePoolType>
 [-ComputerName <String[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-VMStoragePath** cmdlet gets the storage paths in a storage resource pool.

## EXAMPLES

### Example 1
```
PS C:\>Get-VMStoragePath -ResourcePoolName VHD1 -ResourcePoolType VHD
```

Gets the storage paths from virtual hard drive resource pool VHD1.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts on which storage paths are to be retrieved.
NetBIOS names, IP addresses, and fully-qualified domain names are allowable.
The default is the local computer - use "localhost" or a dot (".") to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: .
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path
Specifies the path for which matching storage paths are to be retrieved.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ResourcePoolName
Specifies the name of the resource pool for which storage paths are to be retrieved.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourcePoolType
Specifies the type of the resource pool for which storage paths are to be retrieved.
Valid values are: 

- Memory
- Processor
- Ethernet
- VHD
- ISO
- VFD
- FibreChannelPort
- FibreChannelConnection

```yaml
Type: VMResourcePoolType
Parameter Sets: (All)
Aliases: 
Accepted values: Memory, Processor, Ethernet, VHD, ISO, VFD, FibreChannelPort, FibreChannelConnection

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### System.String

## NOTES

## RELATED LINKS

