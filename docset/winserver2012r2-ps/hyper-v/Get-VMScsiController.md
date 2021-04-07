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
online version: https://docs.microsoft.com/powershell/module/hyper-v/get-vmscsicontroller?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-VMScsiController
---

# Get-VMScsiController

## SYNOPSIS
Gets the SCSI controllers of a virtual machine or snapshot.

## SYNTAX

### VMName (Default)
```
Get-VMScsiController [-ComputerName <String[]>] [-VMName] <String[]> [[-ControllerNumber] <Int32>]
 [<CommonParameters>]
```

### VMSnapshot
```
Get-VMScsiController [-VMSnapshot] <VMSnapshot> [[-ControllerNumber] <Int32>] [<CommonParameters>]
```

### VMObject
```
Get-VMScsiController [[-ControllerNumber] <Int32>] [-VM] <VirtualMachine[]> [<CommonParameters>]
```

## DESCRIPTION
The **Get-VMScsiController** cmdlet gets the SCSI controllers of a virtual machine or snapshot.

## EXAMPLES

### Example 1
```
PS C:\>Get-VMScsiController -VMName TestVM -ControllerNumber 0
```

Gets SCSI controller 0 from virtual machine TestVM.

### Example 2
```
PS C:\>Get-VM -Name TestVM -ComputerName Development | Get-VMScsiController
```

Gets the SCSI controllers from virtual machine TestVM on Hyper-V host Development.

### Example 3
```
PS C:\>Get-VMSnapshot -VMName TestVM -Name 'Before applying updates' | Get-VMScsiController
```

Gets the SCSI controllers from snapshot Before applying updates of virtual machine TestVM.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts on which the SCSI controllers are to be retrieved.
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
Specifies the number of the SCSI controller to be retrieved.

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
Specifies the virtual machine whose SCSI controllers are to be retrieved.

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
Specifies the name of the virtual machine whose SCSI controllers are to be retrieved.

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
Specifies the snapshot whose SCSI controllers are to be retrieved.

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

