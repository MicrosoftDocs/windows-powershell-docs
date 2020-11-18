---
external help file: Microsoft.HyperV.PowerShell.dll-Help.xml
Module Name: Hyper-V
online version: 
schema: 2.0.0
title: Get-VMIdeController
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 1668FD0C-42B1-4E09-A9CF-7EEF76B967AE
---

# Get-VMIdeController

## SYNOPSIS
Gets the IDE controllers of a virtual machine or snapshot.

## SYNTAX

### VMName (Default)
```
Get-VMIdeController [-ComputerName <String[]>] [-VMName] <String[]> [[-ControllerNumber] <Int32>]
 [<CommonParameters>]
```

### VMSnapshot
```
Get-VMIdeController [-VMSnapshot] <VMSnapshot> [[-ControllerNumber] <Int32>] [<CommonParameters>]
```

### VMObject
```
Get-VMIdeController [[-ControllerNumber] <Int32>] [-VM] <VirtualMachine[]> [<CommonParameters>]
```

## DESCRIPTION
The **Get-VMIdeController** cmdlet gets the IDE controllers of a virtual machine or snapshot.

## EXAMPLES

### Example 1
```
PS C:\>Get-VMIdeController TestVM
```

Gets all IDE controllers belonging to virtual machine TestVM.

### Example 2
```
PS C:\>Get-VMIdeController TestVM -ControllerNumber 0
```

Gets the first IDE controller belonging to virtual machine TestVM.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts on which the IDE controllers of a virtual machine or snapshot are to be retrieved.
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

### -ControllerNumber
Specifies the number of the IDE controller to be retrieved.
Allowed values are 0 and 1.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VM
Specifies the virtual machine whose IDE controllers are to be retrieved.

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
Specifies the name of the virtual machine whose IDE controllers are to be retrieved.

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
Specifies the snapshot whose IDE controllers are to be retrieved.

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

### Microsoft.HyperV.PowerShell.IDEController

## NOTES

## RELATED LINKS

