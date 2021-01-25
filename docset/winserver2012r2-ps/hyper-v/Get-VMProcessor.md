---
external help file: Microsoft.HyperV.PowerShell.dll-Help.xml
Module Name: Hyper-V
online version: 
schema: 2.0.0
title: Get-VMProcessor
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 9612A436-8464-4FEF-A86C-CFBCA4F9A537
---

# Get-VMProcessor

## SYNOPSIS
Gets the processor of a virtual machine or snapshot.

## SYNTAX

### VMName (Default)
```
Get-VMProcessor [-ComputerName <String[]>] [-VMName] <String[]> [<CommonParameters>]
```

### VMSnapshot
```
Get-VMProcessor [-VMSnapshot] <VMSnapshot> [<CommonParameters>]
```

### VMObject
```
Get-VMProcessor [-VM] <VirtualMachine[]> [<CommonParameters>]
```

## DESCRIPTION
The **Get-VMProcessor** cmdlet gets the processor of a virtual machine or snapshot.

## EXAMPLES

### Example 1
```
PS C:\>Get-VMProcessor TestVM
```

Gets the processor object for virtual machine TestVM.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts on which the processor of a virtual machine or snapshot is to be retrieved.
NetBIOS names, IP addresses, and fully-qualified domain names are allowable.
The default is the local computer - use "localhost" or a dot (".") to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: VMName
Aliases: 

Required: False
Position: Named
Default value: .
Accept pipeline input: False
Accept wildcard characters: False
```

### -VM
Specifies the virtual machine whose processor is to be retrieved.

```yaml
Type: VirtualMachine[]
Parameter Sets: VMObject
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMName
Specifies the name of the virtual machine whose processor is to be retrieved.

```yaml
Type: String[]
Parameter Sets: VMName
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMSnapshot
Specifies the snapshot whose processor is to be retrieved.

```yaml
Type: VMSnapshot
Parameter Sets: VMSnapshot
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.HyperV.PowerShell.Processor

## NOTES

## RELATED LINKS

