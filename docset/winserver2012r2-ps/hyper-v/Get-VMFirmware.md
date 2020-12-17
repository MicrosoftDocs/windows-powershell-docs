---
external help file: Microsoft.HyperV.PowerShell.dll-Help.xml
Module Name: Hyper-V
online version: 
schema: 2.0.0
title: Get-VMFirmware
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
ms.assetid: C54AB7B1-0AAE-4493-8E51-166CC40E1AAB
---

# Get-VMFirmware

## SYNOPSIS
Gets the firmware configuration of a virtual machine.

## SYNTAX

### VMName (Default)
```
Get-VMFirmware [-ComputerName <String[]>] [-VMName] <String[]> [<CommonParameters>]
```

### VMSnapshot
```
Get-VMFirmware [-VMSnapshot] <VMSnapshot> [<CommonParameters>]
```

### VMObject
```
Get-VMFirmware [-VM] <VirtualMachine[]> [<CommonParameters>]
```

## DESCRIPTION
The **Get-VMFirmware** cmdlet gets the firmware configuration of a virtual machine.
Note: This cmdlet is supported only on Generation 2 virtual machines.

## EXAMPLES

### Example 1
```
PS C:\> Get-VMFirmware "Test VM"
```

This example returns a virtual machine firmware object for the virtual machine "Test VM".

## PARAMETERS

### -ComputerName
Specifies an array of Hyper-V hosts.
The cmdlet gets the virtual machine firmware from the hosts you specify.

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
Specifies an array of virtual machine objects.
The cmdlet gets the firmware configuration for the virtual machines you specify.
To obtain a virtual machine object, use the Get-VM cmdlet.

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
Specifies an array of names of virtual machines.
The cmdlet gets the firmware configuration for the virtual machines you specify.

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
Specifies the virtual machine snapshot to be used with the VM when retrieving the firmware configuration.

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

### Microsoft.HyperV.PowerShell.VMFirmware

## NOTES
* Note: This cmdlet is supported only on Generation 2 virtual machines.

## RELATED LINKS

[Set-VMFirmware](./Set-VMFirmware.md)

