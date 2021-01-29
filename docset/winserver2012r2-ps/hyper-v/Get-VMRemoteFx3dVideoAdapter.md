---
external help file: Microsoft.HyperV.PowerShell.dll-Help.xml
Module Name: Hyper-V
online version: 
schema: 2.0.0
title: Get-VMRemoteFx3dVideoAdapter
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 082B9173-FC0C-4535-B034-DA69F03AA0C8
---

# Get-VMRemoteFx3dVideoAdapter

## SYNOPSIS
Gets the RemoteFX video adapter of a virtual machine or snapshot.

## SYNTAX

### VMName (Default)
```
Get-VMRemoteFx3dVideoAdapter [-ComputerName <String[]>] [-VMName] <String[]> [<CommonParameters>]
```

### VMSnapshot
```
Get-VMRemoteFx3dVideoAdapter [-VMSnapshot] <VMSnapshot> [<CommonParameters>]
```

### VMObject
```
Get-VMRemoteFx3dVideoAdapter [-VM] <VirtualMachine[]> [<CommonParameters>]
```

## DESCRIPTION
The **Get-VMRemoteFx3dVideoAdapter** cmdlet gets the RemoteFX video adapter of a virtual machine or snapshot.

## EXAMPLES

### Example 1
```
PS C:\>Get-VMRemoteFx3dVideoAdapter -VMName TestVM
```

Gets the RemoteFX adapter from virtual machine TestVM.

### Example 2
```
PS C:\>Get-VM -Name TestVM | Get-VMRemoteFx3dVideoAdapter
```

Gets the RemoteFx adapter from virtual machine TestVM.

### Example 3
```
PS C:\>Get-VMSnapshot -VMName TestVM -Name 'Before applying updates' | Get-VMRemoteFx3dVideoAdapter
```

Gets the RemoteFx adapter from snapshot Before applying updates of virtual machine TestVM.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts on which the RemoteFX video adapter is to be retrieved.
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
Specifies the virtual machine whose RemoteFX video adapter is to be retrieved.

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
Specifies the name of the virtual machine whose RemoteFX video adapter is to be retrieved.

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
Specifies the snapshot whose RemoteFX video adapter is to be retrieved.

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

### Microsoft.HyperV.PowerShell.RemoteFxVideoAdapter

## NOTES

## RELATED LINKS

