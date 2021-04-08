---
author: Kateyanne
description: 
external help file: Microsoft.HyperV.PowerShell.dll-Help.xml
manager: jasgro
Module Name: Hyper-V
ms.author: v-kaunu
ms.date: 10/30/2017
ms.prod: powershell
ms.reviewer: brianlic
ms.topic: reference
online version: https://docs.microsoft.com/powershell/module/hyper-v/get-vmfibrechannelhba?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-VMFibreChannelHba
---

# Get-VMFibreChannelHba

## SYNOPSIS
Gets the Fibre Channel host bus adapters associated with one or more virtual machines.

## SYNTAX

### VMName (Default)
```
Get-VMFibreChannelHba [-ComputerName <String[]>] [-VMName] <String[]> [<CommonParameters>]
```

### VMObject
```
Get-VMFibreChannelHba [-VM] <VirtualMachine[]> [<CommonParameters>]
```

## DESCRIPTION
Lists all of the fibre channel objects for each virtual fibre channel controller that is connected to the specified virtual machine.

## EXAMPLES

### Example 1
```
PS C:\>Get-VMFibreChannelHba -VMName MyVM
```

Gets the Fibre Channel host bus adapters associated with the virtual machine MyVM.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts on which the Fibre Channel host bus adapters are to be retrieved.
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
Specifies a virtual machine or machines for which the Fibre Channel host bus adapters are to be retrieved.

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
Specifies the friendly name or names of the virtual machines for which the Fibre Channel host bus adapters are to be retrieved.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

