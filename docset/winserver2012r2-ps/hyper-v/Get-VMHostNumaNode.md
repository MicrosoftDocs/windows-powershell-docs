---
external help file: Microsoft.HyperV.PowerShell.dll-Help.xml
Module Name: Hyper-V
online version: 
schema: 2.0.0
title: Get-VMHostNumaNode
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: AC4710F8-8CFD-4975-92EB-84675A025662
---

# Get-VMHostNumaNode

## SYNOPSIS
Gets the NUMA topology of a virtual machine host.

## SYNTAX

```
Get-VMHostNumaNode [[-ComputerName] <String[]>] [-Id <Int32>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-MVHostNumaNode** cmdlet gets the NUMA topology of a Hyper-V host, returning a **VMHostNumaNode** object for each of the host's NUMA nodes.

## EXAMPLES

### Example 1
```
PS C:\>Get-VMHostNumaNode
```

Gets the NUMA topology of the local Hyper-V host.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts for which the NUMA topology is to be retrieved.
NetBIOS names, IP addresses, and fully-qualified domain names are allowable.
The default is the local computer - use "localhost" or a dot (".") to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: .
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Id
Identifies a NUMA node for which a **VMHostNumaNode** is to be retrieved.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

