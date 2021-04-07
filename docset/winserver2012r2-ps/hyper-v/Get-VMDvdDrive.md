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
online version: https://docs.microsoft.com/powershell/module/hyper-v/get-vmdvddrive?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-VMDvdDrive
---

# Get-VMDvdDrive

## SYNOPSIS
Gets the DVD drives attached to a virtual machine or snapshot.

## SYNTAX

### VMName (Default)
```
Get-VMDvdDrive [-ControllerLocation <Int32>] [-ControllerNumber <Int32>] [-ComputerName <String[]>]
 [-VMName] <String[]> [<CommonParameters>]
```

### VMObject
```
Get-VMDvdDrive [-ControllerLocation <Int32>] [-ControllerNumber <Int32>] [-VM] <VirtualMachine[]>
 [<CommonParameters>]
```

### VMSnapshot
```
Get-VMDvdDrive [-ControllerLocation <Int32>] [-ControllerNumber <Int32>] [-VMSnapshot] <VMSnapshot>
 [<CommonParameters>]
```

### VMDriveController
```
Get-VMDvdDrive [-ControllerLocation <Int32>] [-VMDriveController] <VMDriveController[]> [<CommonParameters>]
```

## DESCRIPTION
The **Get-VMDvdDrive** cmdlet gets the DVD drives attached to a virtual machine or snapshot.
This cmdlet has no ControllerType parameter, as the Get-VMHardDiskDrive cmdlet does, because virtual DVD drives can be attached only to the IDE controller.

## EXAMPLES

### Example 1
```
PS C:\>Get-VMDvdDrive -VMName Test
```

Gets the virtual DVD drives from virtual machine Test.

### Example 2
```
PS C:\>Get-VM -Name Test | Get-VMDvdDrive -ControllerNumber 1
```

Gets the virtual DVD drives from IDE controller 1 of virtual machine Test.

### Example 3
```
PS C:\>Get-VMIdeController -VMName TestVM -ControllerNumber 1 -ComputerName Development | Get-VMDvdDrive
```

Gets the virtual DVD drives from IDE controller 1 of virtual machine TestVM located on Hyper-V server Development.

### Example 4
```
PS C:\>Get-VMSnapshot -VMName TestVM -Name 'Before applying updates' | Get-VMDvdDrive
```

Gets the virtual DVD drives from snapshot Before applying updates of virtual machine TestVM.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts from which the DVD drives are to be retrieved.
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

### -ControllerLocation
Specifies the number of the location on the controller from which the DVD drives are to be retrieved.

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

### -ControllerNumber
Specifies the number of the controller from which the DVD drives are to be retrieved.

```yaml
Type: Int32
Parameter Sets: VMName, VMObject, VMSnapshot
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VM
Specifies the virtual machine from which the DVD drives are to be retrieved.

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

### -VMDriveController
Specifies the controller from which the DVD drives are to be retrieved.

```yaml
Type: VMDriveController[]
Parameter Sets: VMDriveController
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMName
Specifies the name of the virtual machine from which the DVD drives are to be retrieved.

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
Specifies the virtual machine snapshot from which the DVD drives are to be retrieved.

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

### Microsoft.HyperV.PowerShell.VMDriveController[]

### Microsoft.HyperV.PowerShell.VMSnapshot

### Microsoft.HyperV.PowerShell.VirtualMachine[]

## OUTPUTS

### Microsoft.HyperV.PowerShell.DvdDrive

## NOTES

## RELATED LINKS

