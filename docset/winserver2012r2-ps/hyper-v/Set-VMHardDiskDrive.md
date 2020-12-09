---
external help file: Microsoft.HyperV.PowerShell.dll-Help.xml
Module Name: Hyper-V
online version: 
schema: 2.0.0
title: Set-VMHardDiskDrive
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
ms.assetid: F3269885-AB4C-408D-8924-7B4484B4D9A3
---

# Set-VMHardDiskDrive

## SYNOPSIS
Configures a virtual hard disk.

## SYNTAX

### VMName (Default)
```
Set-VMHardDiskDrive [-ComputerName <String[]>] [-VMName] <String> [[-ControllerType] <ControllerType>]
 [[-ControllerNumber] <Int32>] [[-ControllerLocation] <Int32>] [[-Path] <String>]
 [-ToControllerType <ControllerType>] [-ToControllerNumber <Int32>] [-ToControllerLocation <Int32>]
 [-DiskNumber <UInt32>] [-ResourcePoolName <String>] [-SupportPersistentReservations <Boolean>]
 [-AllowUnverifiedPaths] [-MaximumIOPS <UInt64>] [-MinimumIOPS <UInt64>] [-Passthru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### Object
```
Set-VMHardDiskDrive [-ComputerName <String[]>] [-VMHardDiskDrive] <HardDiskDrive[]> [[-Path] <String>]
 [-ToControllerType <ControllerType>] [-ToControllerNumber <Int32>] [-ToControllerLocation <Int32>]
 [-DiskNumber <UInt32>] [-ResourcePoolName <String>] [-SupportPersistentReservations <Boolean>]
 [-AllowUnverifiedPaths] [-MaximumIOPS <UInt64>] [-MinimumIOPS <UInt64>] [-Passthru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-VMHardDiskDrive** cmdlet configures a virtual hard disk.

## EXAMPLES

### Example 1
```
PS C:\> Set-VMHardDiskDrive -VMName TestVM -Path .\Test.vhd
```

Configures the hard drive of virtual machine TestVM to use Test.vhd as its media.

### Example 2
```
PS C:\> Get-VMHardDiskDrive -VMName TestVM -ControllerType IDE -ControllerNumber 1 -ControllerLocation 0 | Set-VMHardDiskDrive -ToControllerLocation 1
```

Moves the virtual hard drive on virtual machine TestVM from IDE 1,0 to IDE 1,1.

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
Specifies one or more Hyper-V hosts on which the virtual hard drive is to be configured.
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
Specifies the number of the location on the controller to which the virtual hard drive to be configured is attached.
If not specified, all hard drives are configured.

```yaml
Type: Int32
Parameter Sets: VMName
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ControllerNumber
Specifies the number of the controller to which the virtual hard drive to be configured is attached.
If not specified, all hard drives are configured.

```yaml
Type: Int32
Parameter Sets: VMName
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ControllerType
Specifies the type of the controller to which the virtual hard drive to be configured is attached.
Allowed values are **Floppy**, **IDE**, and **SCSI**.

```yaml
Type: ControllerType
Parameter Sets: VMName
Aliases: 
Accepted values: IDE, SCSI, Floppy

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DiskNumber
Specifies the disk number of the offline physical hard drive that should be connected as a passthrough disk.

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
Specifies that a **Microsoft.HyperV.PowerShell.HardDiskDrive** object is to be passed through to the pipeline representing the virtual hard drive to be configured.

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
Specifies the path to media the virtual hard disk is to use.

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
Specifies the name of the virtual hard disk resource pool to which this drive belongs.

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
Indicates whether the hard disk supports SCSI persistent reservation semantics.
Specify this parameter when the hard disk is a shared disk that is used by multiple virtual machines.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: ShareVirtualDisk

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ToControllerLocation
Specifies the controller location to which this drive should be moved.
Allowed values are 0 and 1 for IDE controllers, and from 0 to 63 for SCSI controllers.

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

### -ToControllerNumber
Specifies the controller location to which this drive should be moved.
Allowed values are 0 and 1 for IDE controllers, and from 0 to 3 for SCSI controllers.

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

### -ToControllerType
Specifies the type of controller to which this drive should be moved.
Allowed values are IDE and SCSI.

```yaml
Type: ControllerType
Parameter Sets: (All)
Aliases: 
Accepted values: IDE, SCSI, Floppy

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMHardDiskDrive
Specifies one or more hard disks to be configured.

```yaml
Type: HardDiskDrive[]
Parameter Sets: Object
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMName
Specifies the name of the virtual machine on which the virtual hard drive is to be configured.

```yaml
Type: String
Parameter Sets: VMName
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
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

## OUTPUTS

## NOTES

## RELATED LINKS

