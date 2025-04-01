---
external help file: VMDirectStorage-help.xml
Module Name: VMDirectStorage
ms.date: 03/28/2025
online version: https://learn.microsoft.com/powershell/module/vmdirectstorage/get-vmdirectvirtualdisk?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-VMDirectVirtualDisk
ai-usage: ai-generated
---

# Get-VMDirectVirtualDisk

## Synopsis

Retrieves information about Storage Spaces Direct virtual disks attached to a virtual machine.

## Syntax

### ByVMName

```
Get-VMDirectVirtualDisk [-VMName] <String[]> [-CimSession <CimSession[]>] [[-ControllerType] <ControllerType>]
 [[-ControllerNumber] <Int32>] [-ControllerLocation <Int32>] [<CommonParameters>]
```

### ByVM

```
Get-VMDirectVirtualDisk [-VM] <VirtualMachine[]> [[-ControllerType] <ControllerType>]
 [[-ControllerNumber] <Int32>] [-ControllerLocation <Int32>] [<CommonParameters>]
```

### ByVMDriveController

```
Get-VMDirectVirtualDisk [-VMDriveController] <VMDriveController[]> [-ControllerLocation <Int32>]
 [<CommonParameters>]
```

## Description

The **Get-VMDirectVirtualDisk** cmdlet retrieves information about Storage Spaces Direct virtual
disks attached to a virtual machine. This includes details such as the disk's unique ID, friendly
name, and its location on the controller.

## Examples

### Example 1: Retrieve virtual disks by virtual machine name

This command retrieves all virtual disks attached to the virtual machine named "VM1".

```powershell
Get-VMDirectVirtualDisk -VMName "VM1"
```

```Output
VMName ControllerType ControllerNumber ControllerLocation VirtualDiskFriendlyName VirtualDiskUniqueId
------ -------------- ---------------- ------------------ ----------------------- -------------------
VM1    SCSI           0                1                  Volume01                111BBE22FD037E4E...
```

### Example 2: Retrieve virtual disks by virtual machine object

This command gets the virtual machine object for "VM1" and then retrieves its directly attached
virtual disks.

```powershell
$vm = Get-VM -Name "VM1"
Get-VMDirectVirtualDisk -VM $vm
```

## Parameters

### -CimSession

Runs the command using the specified CIM session. Enter a variable that contains the CIM session, or
a command that creates or gets the CIM session, such as `New-CimSession` or `Get-CimSession`. For more
information, see
[about_CimSession](/powershell/module/microsoft.powershell.core/about/about_cimsession).

```yaml
Type: Microsoft.Management.Infrastructure.CimSession[]
Parameter Sets: ByVMName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ControllerLocation

Specifies the location of the virtual disk on the controller.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ControllerNumber

Specifies the number of the controller where the virtual disk is attached.

```yaml
Type: System.Int32
Parameter Sets: ByVMName, ByVM
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ControllerType

Specifies the type of controller. Only SCSI is supported.

```yaml
Type: ControllerType
Parameter Sets: ByVMName, ByVM
Aliases:
Accepted values: SCSI

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VM

Specifies the virtual machine object for which to retrieve virtual disk information.

```yaml
Type: Microsoft.HyperV.PowerShell.VirtualMachine[]
Parameter Sets: ByVM
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMDriveController

Specifies the drive controller object for which to retrieve virtual disk information.

```yaml
Type: Microsoft.HyperV.PowerShell.VMDriveController[]
Parameter Sets: ByVMDriveController
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMName

Specifies the name of the virtual machine for which to retrieve virtual disk information.

```yaml
Type: System.String[]
Parameter Sets: ByVMName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## Inputs

### System.String[]

Specifies the names of virtual machines.

### Microsoft.HyperV.PowerShell.VirtualMachine[]

Specifies virtual machine objects.

### Microsoft.HyperV.PowerShell.VMDriveController[]

Specifies drive controller objects.

## Outputs

### VMDirectVirtualDisk

Returns objects representing the virtual disks attached to the specified virtual machine.

## Notes

## Related links

- [Add-VMDirectVirtualDisk](Add-VMDirectVirtualDisk.md)

- [Remove-VMDirectVirtualDisk](Remove-VMDirectVirtualDisk.md)
