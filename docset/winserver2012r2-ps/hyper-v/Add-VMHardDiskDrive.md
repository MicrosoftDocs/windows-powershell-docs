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
online version: https://docs.microsoft.com/powershell/module/hyper-v/add-vmharddiskdrive?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-VMHardDiskDrive
---

# Add-VMHardDiskDrive

## SYNOPSIS
Adds a hard disk drive to a virtual machine.

## SYNTAX

### VMName (Default)
```
Add-VMHardDiskDrive [-ComputerName <String[]>] [[-ControllerType] <ControllerType>]
 [[-ControllerNumber] <Int32>] [[-ControllerLocation] <Int32>] [[-Path] <String>] [-DiskNumber <UInt32>]
 [-ResourcePoolName <String>] [-SupportPersistentReservations] [-AllowUnverifiedPaths] [-MaximumIOPS <UInt64>]
 [-MinimumIOPS <UInt64>] [-Passthru] [-VMName] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### VMDriveController
```
Add-VMHardDiskDrive [-ComputerName <String[]>] [-VMDriveController] <VMDriveController>
 [[-ControllerLocation] <Int32>] [[-Path] <String>] [-DiskNumber <UInt32>] [-ResourcePoolName <String>]
 [-SupportPersistentReservations] [-AllowUnverifiedPaths] [-MaximumIOPS <UInt64>] [-MinimumIOPS <UInt64>]
 [-Passthru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### VMObject
```
Add-VMHardDiskDrive [-ComputerName <String[]>] [[-ControllerType] <ControllerType>]
 [[-ControllerNumber] <Int32>] [[-ControllerLocation] <Int32>] [[-Path] <String>] [-DiskNumber <UInt32>]
 [-ResourcePoolName <String>] [-SupportPersistentReservations] [-AllowUnverifiedPaths] [-MaximumIOPS <UInt64>]
 [-MinimumIOPS <UInt64>] [-Passthru] [-VM] <VirtualMachine[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Add-VMHardDiskDrive** cmdlet adds a hard disk drive to a virtual machine.

## EXAMPLES

### Example 1
```
PS C:\>Add-VMHardDiskDrive -VMName Test -Path D:\VHDs\disk1.vhdx
```

Creates a virtual hard disk using file D:\VHDs\disk1.vhdx on virtual machine Test.

### Example 2
```
PS C:\>Get-VM Test | Add-VMHardDiskDrive -ControllerType SCSI -ControllerNumber 0
```

Adds a virtual hard disk to SCSI controller number 0 on virtual machine Test.

### Example 3
```
PS C:\>Get-VMScsiController -VMName Test -Number 0 | Add-VMHardDiskDrive -DiskNumber 2
```

This example gets a SCSI controller on a virtual machine named Test and then adds physical disk 2 to that controller.

### Example 4
```
PS C:\>Get-Disk 2 | Add-VMHardDiskDrive -VMName Test
```

This example gets physical disk 2 and then adds it to a virtual machine named Test.

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
Specifies one or more virtual machine hosts on which the hard disk drive is to be added.
NetBIOS names, IP addresses, and fully-qualified domain names are allowable.
The default is the local computer - use "localhost" or a dot (".") to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: PSComputerName

Required: False
Position: Named
Default value: .
Accept pipeline input: True (ByPropertyName)
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
Specifies the number of the location on the controller at which the hard disk drive is to be added.
If not specified, the first available location in the controller specified with the **ControllerNumber** parameter is used.

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
Specifies the number of the controller to which the hard disk drive is to be added.
If not specified, this parameter assumes the value of the first available controller at the location specified in the **ControllerLocation** parameter.

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

### -ControllerType
Specifies the type of the controller to which the hard disk drive is to be added.
If not specified, **IDE** is attempted first.
If the IDE controller port at the specified number and location is already connected to a drive, then it will try to create one on the SCSI controller specified by **ControllerNumber**.
Allowed values are **IDE** and **SCSI**.

```yaml
Type: ControllerType
Parameter Sets: VMName, VMObject
Aliases: 
Accepted values: IDE, SCSI, Floppy

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DiskNumber
Specifies the disk number of the offline physical hard drive to be connected as a passthrough disk.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: Number

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MaximumIOPS
Specifies the maximum normalized I/O operations per second (IOPS) for the hard disk.
Hyper-V calculates normalized IOPS as the total size of I/O per second divided by 8 KB.

```yaml
Type: UInt64
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MinimumIOPS
Specifies the minimum normalized I/O operations per second (IOPS) for the hard disk.
Hyper-V calculates normalized IOPS as the total size of I/O per second divided by 8 KB.

```yaml
Type: UInt64
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Passthru
Passes the added **Microsoft.HyperV.PowerShell.HardDiskDrive** object through to the pipeline.

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
Specifies the full path of the hard disk drive file to be added.

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
Specifies the friendly name of the ISO resource pool to which this virtual hard disk is to be associated.

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

### -SupportPersistentReservations
Indicates that the hard disk supports SCSI persistent reservation semantics.
Specify this parameter when the hard disk is a shared disk that is used by multiple virtual machines.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: ShareVirtualDisk

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VM
Specifies the virtual machine to which the hard disk drive is to be added.

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
Specifies the controller to which the hard disk drive is to be added.

```yaml
Type: VMDriveController
Parameter Sets: VMDriveController
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMName
Specifies the name of the virtual machine to which the hard disk drive is to be added.

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

### Microsoft.HyperV.Powershell.DriveController[]

### Microsoft.HyperV.Powershell.VirtualMachine[]

## OUTPUTS

###  
None by default; **Microsoft.HyperV.PowerShell.HardDiskDrive** if **-PassThru** is specified.

## NOTES

## RELATED LINKS

