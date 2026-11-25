---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.HyperV.PowerShell.Cmdlets.dll-Help.xml
Module Name: Hyper-V
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hyper-v/get-vmharddiskdrive?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-VMHardDiskDrive
---

# Get-VMHardDiskDrive

## SYNOPSIS
Gets the virtual hard disk drives attached to one or more virtual machines.

## SYNTAX

### VMName (Default)
```
Get-VMHardDiskDrive [-CimSession <CimSession[]>] [-ComputerName <String[]>] [-Credential <PSCredential[]>]
 [-VMName] <String[]> [-ControllerLocation <Int32>] [-ControllerNumber <Int32>]
 [-ControllerType <ControllerType>] [<CommonParameters>]
```

### VMObject
```
Get-VMHardDiskDrive [-VM] <VirtualMachine[]> [-ControllerLocation <Int32>] [-ControllerNumber <Int32>]
 [-ControllerType <ControllerType>] [<CommonParameters>]
```

### VMSnapshot
```
Get-VMHardDiskDrive [-VMSnapshot] <VMSnapshot> [-ControllerLocation <Int32>] [-ControllerNumber <Int32>]
 [-ControllerType <ControllerType>] [<CommonParameters>]
```

### VMDriveController
```
Get-VMHardDiskDrive [-ControllerLocation <Int32>] [-VMDriveController] <VMDriveController[]>
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-VMHardDiskDrive** cmdlet gets the virtual hard disk drives attached to one or more virtual machines.

## EXAMPLES

### Example 1
```
PS C:\> Get-VMHardDiskDrive -VMName TestVM
```

Gets the virtual hard drives from virtual machine TestVM.

### Example 2
```
PS C:\> Get-VM -Name TestVM | Get-VMHardDiskDrive -ControllerType IDE -ControllerNumber 1
```

Gets the virtual hard drives from IDE controller 1 of virtual machine TestVM.

### Example 3
```
PS C:\> Get-VMIdeController -VMName TestVM -ControllerNumber 1 -ComputerName Development | Get-VMHardDiskDrive
```

Gets the virtual hard drives from IDE controller 1 of virtual machine TestVM located on Hyper-V host Development.

### Example 4
```
PS C:\> Get-VMSnapshot -VMName Test -Name 'Before applying updates' | Get-VMHardDiskDrive
```

Gets the virtual hard drives from snapshot Before applying updates of virtual machine TestVM.

## PARAMETERS

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
Specifies one or more Hyper-V hosts from which the virtual hard disk drives are to be retrieved.
NetBIOS names, IP addresses, and fully qualified domain names are allowable.
The default is the local computer.
Use localhost or a dot (.) to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: VMName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ControllerLocation
Specifies the number of the location on the controller at which the virtual hard disk drives are to be retrieved.
If not specified, the number of the first available location on the controller is used.

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
Specifies the number of the controller at which the virtual hard disk drives are to be retrieved.
If not specified, the first controller on which the specified **ControllerLocation** is available is used.

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

### -ControllerType
Specifies the type of the controller from which the virtual hard disk drives are to be retrieved.
Allowed values are **Floppy**, **IDE**, and **SCSI**.

```yaml
Type: ControllerType
Parameter Sets: VMName, VMObject, VMSnapshot
Aliases:
Accepted values: IDE, SCSI

Required: False
Position: Named
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

### -VM
Specifies the virtual machine from which the virtual hard disk drives are to be retrieved.

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
Specifies the drive controller from which the virtual hard disk drives are to be retrieved.

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
Specifies the name of the virtual machine from which the virtual hard disks drives are to be retrieved.

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
Specifies the snapshot from which the virtual hard disk drives are to be retrieved.

```yaml
Type: VMSnapshot
Parameter Sets: VMSnapshot
Aliases: VMCheckpoint

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.HyperV.PowerShell.ControllerType

### Microsoft.HyperV.PowerShell.VMSnapshot

### Microsoft.HyperV.PowerShell.VMDriveController[]

### Microsoft.HyperV.PowerShell.VirtualMachine[]

## OUTPUTS

### Microsoft.HyperV.PowerShell.HardDiskDrive

## NOTES

## RELATED LINKS

