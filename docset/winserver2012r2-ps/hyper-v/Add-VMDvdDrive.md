---
external help file: Microsoft.HyperV.PowerShell.dll-Help.xml
Module Name: Hyper-V
online version: 
schema: 2.0.0
title: Add-VMDvdDrive
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
ms.assetid: CD561A26-E7EA-4B6D-A458-2404CB6B7C91
---

# Add-VMDvdDrive

## SYNOPSIS
Adds a DVD drive to a virtual machine.

## SYNTAX

### VMName (Default)
```
Add-VMDvdDrive [[-ControllerNumber] <Int32>] [[-ControllerLocation] <Int32>] [[-Path] <String>]
 [-ResourcePoolName <String>] [-AllowUnverifiedPaths] [-Passthru] [-ComputerName <String[]>]
 [-VMName] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### VMDriveController
```
Add-VMDvdDrive [-VMDriveController] <VMDriveController[]> [[-ControllerLocation] <Int32>] [[-Path] <String>]
 [-ResourcePoolName <String>] [-AllowUnverifiedPaths] [-Passthru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### VMObject
```
Add-VMDvdDrive [[-ControllerNumber] <Int32>] [[-ControllerLocation] <Int32>] [[-Path] <String>]
 [-ResourcePoolName <String>] [-AllowUnverifiedPaths] [-Passthru] [-VM] <VirtualMachine[]> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Add-VMDvdDrive** cmdlet adds a DVD drive to a virtual machine.

## EXAMPLES

### Example 1
```
PS C:\>Add-VMDvdDrive -VMName Test -Path D:\ISOs\disc1.iso
```

This example adds a virtual DVD drive using file D:\ISOs\disc1.iso to virtual machine Test.

### Example 2
```
PS C:\>Get-VM Test | Add-VMDvdDrive -ControllerNumber 1
```

This example adds a virtual DVD drive using controller number 1 to virtual machine Test.

### Example 3
```
PS C:\>Get-VMIdeController -VMName Test | Add-VMDvdDrive -Path E:\
```

This example adds virtual DVD drives using the IDE controllers from virtual machine Test.

## PARAMETERS

### -AllowUnverifiedPaths
Specifies that no error is to be thrown if the specified path is not verified as accessible by the cluster.
This parameter is applicable to clustered virtual machines.

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

### -ComputerName
Specifies one or more Hyper-v hosts on which the DVD drive is to be added.
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

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -ControllerLocation
Specifies the number of the location on the controller at which the DVD drive is to be added.
If not specified, the number of the first available location on the controller is used.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ControllerNumber
Specifies the number of the controller to which the DVD drive is to be added.
If not specified, the first IDE controller on which the specified **ControllerLocation** is available is used.

```yaml
Type: Int32
Parameter Sets: VMName, VMObject
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Passthru
Passes the added **Microsoft.HyperV.PowerShell.DvdDrive** through to the pipeline.

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
Specifies the full path to the virtual hard disk file or physical hard disk volume for the added DVD drive.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourcePoolName
Specifies the friendly name of the ISO resource pool to which this DVD drive is to be associated.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VM
Specifies the virtual machine to which the DVD drive is to be added.

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
Specifies the drive controller to which the DVD drive is to be added.

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
Specifies the name of the virtual machine to which the DVD drive is to be added.

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

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.HyperV.PowerShell.VMDriveController[]

### Microsoft.HyperV.PowerShell.VirtualMachine[]

## OUTPUTS

### Microsoft.HyperV.PowerShell.DvdDrive

## NOTES

## RELATED LINKS

