---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.HyperV.PowerShell.Cmdlets.dll-Help.xml
Module Name: Hyper-V
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hyper-v/add-vmharddiskdrive?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-VMHardDiskDrive
---

# Add-VMHardDiskDrive

## SYNOPSIS
Adds a hard disk drive to a virtual machine.

## SYNTAX

### VMName (Default)
```
Add-VMHardDiskDrive [-CimSession <CimSession[]>] [-ComputerName <String[]>] [-Credential <PSCredential[]>]
 [-VMName] <String[]> [[-ControllerType] <ControllerType>] [[-ControllerNumber] <Int32>]
 [[-ControllerLocation] <Int32>] [[-Path] <String>] [-DiskNumber <UInt32>] [-ResourcePoolName <String>]
 [-SupportPersistentReservations] [-AllowUnverifiedPaths] [-MaximumIOPS <UInt64>] [-MinimumIOPS <UInt64>]
 [-QoSPolicyID <String>] [-QoSPolicy <CimInstance>] [-Passthru] [-OverrideCacheAttributes <CacheAttributes>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### VMObject
```
Add-VMHardDiskDrive [-VM] <VirtualMachine[]> [[-ControllerType] <ControllerType>] [[-ControllerNumber] <Int32>]
 [[-ControllerLocation] <Int32>] [[-Path] <String>] [-DiskNumber <UInt32>] [-ResourcePoolName <String>]
 [-SupportPersistentReservations] [-AllowUnverifiedPaths] [-MaximumIOPS <UInt64>] [-MinimumIOPS <UInt64>]
 [-QoSPolicyID <String>] [-QoSPolicy <CimInstance>] [-Passthru] [-OverrideCacheAttributes <CacheAttributes>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### VMDriveController
```
Add-VMHardDiskDrive [-VMDriveController] <VMDriveController> [[-ControllerLocation] <Int32>] [[-Path] <String>]
 [-DiskNumber <UInt32>] [-ResourcePoolName <String>] [-SupportPersistentReservations] [-AllowUnverifiedPaths]
 [-MaximumIOPS <UInt64>] [-MinimumIOPS <UInt64>] [-QoSPolicyID <String>] [-QoSPolicy <CimInstance>] [-Passthru]
 [-OverrideCacheAttributes <CacheAttributes>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Add-VMHardDiskDrive** cmdlet adds a hard disk drive to a virtual machine.

## EXAMPLES

### Example 1
```
PS C:\> Add-VMHardDiskDrive -VMName Test -Path D:\VHDs\disk1.vhdx
```

Creates a virtual hard disk using file D:\VHDs\disk1.vhdx on virtual machine Test.

### Example 2
```
PS C:\> Get-VM Test | Add-VMHardDiskDrive -ControllerType SCSI -ControllerNumber 0
```

Adds a virtual hard disk to SCSI controller number 0 on virtual machine Test.

### Example 3
```
PS C:\> Get-VMScsiController -VMName Test -ControllerNumber 0 | Add-VMHardDiskDrive -DiskNumber 2
```

This example gets a SCSI controller on a virtual machine named Test and then adds physical disk 2 to that controller.

### Example 4
```
PS C:\> Get-Disk 2 | Add-VMHardDiskDrive -VMName Test
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

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: VMName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
Specifies one or more Hyper-V hosts that run this cmdlet.
NetBIOS names, IP addresses, and fully qualified domain names are allowable.
The default is the local computer.
Use localhost or a dot (.) to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: VMName
Aliases: PSComputerName

Required: False
Position: Named
Default value: None
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
Accepted values: IDE, SCSI

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
Specifies one or more user accounts that have permission to perform this action.
The default is the current user.

```yaml
Type: PSCredential[]
Parameter Sets: VMName
Aliases:

Required: False
Position: Named
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

### -OverrideCacheAttributes


```yaml
Type: CacheAttributes
Parameter Sets: (All)
Aliases:
Accepted values: Default, WriteCacheEnabled, WriteCacheAndFUAEnabled, WriteCacheDisabled

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

### -QoSPolicy
Specifies the name of the storage Quality of Service (QoS) policy that this cmdlet associates with the hard disk drive.

```yaml
Type: CimInstance
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -QoSPolicyID
Specifies the unique ID for a storage QoS policy that this cmdlet associates with the hard disk drive.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.HyperV.Powershell.DriveController[]

### Microsoft.HyperV.Powershell.VirtualMachine[]

## OUTPUTS

### None
Default

### Microsoft.HyperV.PowerShell.HardDiskDrive
If **-PassThru** is specified.

## NOTES

## RELATED LINKS
