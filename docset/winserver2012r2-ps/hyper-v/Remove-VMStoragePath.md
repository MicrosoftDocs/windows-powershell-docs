---
external help file: Microsoft.HyperV.PowerShell.dll-Help.xml
Module Name: Hyper-V
online version: 
schema: 2.0.0
title: Remove-VMStoragePath
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 6EC679AD-A16B-4078-A68A-3CF76717C713
---

# Remove-VMStoragePath

## SYNOPSIS
Removes a path from a storage resource pool.

## SYNTAX

```
Remove-VMStoragePath [-Path] <String[]> [-ResourcePoolName] <String[]> [-ResourcePoolType] <VMResourcePoolType>
 [-PassThru] [-ComputerName <String[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-VMStoragePath** cmdlet removes a path from a storage resource pool.

## EXAMPLES

### Example 1
```
PS C:\>Remove-VMStoragePath -Path D:\Test -ResourcePoolName VHD1 -ResourcePoolType VHD
```

Removes path D:\Test from VHD resource pool VHD1.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts on which a path is to be removed from a resource pool.
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

### -PassThru
Specifies that a **System.String** is to be passed through to the pipeline representing the path to be removed from the resource pool.

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

### -Path
Specifies the path to be removed from the storage resource pool.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ResourcePoolName
Specifies the name of the resource pool from which the path is to be removed.

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
Specifies the type of the resource pool from which the path is to be removed.
Allowed values are **VFD**, **ISO**, and **VHD**.

```yaml
Type: VMResourcePoolType
Parameter Sets: (All)
Aliases: 
Accepted values: VHD, ISO, VFD

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

###  
None by default; **System.String** if **-PassThru** is specified.

## NOTES

## RELATED LINKS

