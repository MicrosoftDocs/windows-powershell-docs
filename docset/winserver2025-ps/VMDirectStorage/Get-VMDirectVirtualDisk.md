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

### Example 1: Retrieve directly attached virtual disks by VM name

This command retrieves all virtual disks attached to the virtual machine named `VM1` running on the
cluster named `Cluster01`.

```powershell
Get-VMDirectVirtualDisk -VMName "VM1" -CimSession "Cluster01"
```

```Output
VMName ControllerType ControllerNumber ControllerLocation VirtualDiskFriendlyName VirtualDiskUniqueId
------ -------------- ---------------- ------------------ ----------------------- -------------------
VM1    SCSI           0                1                  Volume01                111BBE22FD037E4E...
```

### Example 2: Retrieve directly attached virtual disks by VM object

This command gets the virtual machine object for `VM1` running on `Cluster01` and then retrieves its
directly attached virtual disks.

```powershell
$vm = Get-VM -Name "VM1" -CimSession "Cluster01"
Get-VMDirectVirtualDisk -VM $vm
```

### Example 3: Retrieve virtual disks by drive controller object

This command gets the drive controller object for the virtual machine named `VM1` running on
`Cluster01` and retrieves the directly attached virtual disks.

```powershell
$vm = Get-VM -Name "VM1" -CimSession "Cluster01"
$controller = Get-VMScsiController -VMName "VM1" -CimSession "Cluster01"

Get-VMDirectVirtualDisk -VMDriveController $controller
```

```Output
VMName ControllerType ControllerNumber ControllerLocation VirtualDiskFriendlyName VirtualDiskUniqueId
------ -------------- ---------------- ------------------ ----------------------- -------------------
VM1    SCSI           0                1                  Volume01                111BBE22FD037E4E...
VM1    SCSI           0                2                  Volume02                222BBE22FD037E4E...
```

## Parameters

### -CimSession

Runs the cmdlet in a remote session or on a remote computer. Enter a computer name, cluster name, or
a session object, such as the output of a `New-CimSession` or `Get-CimSession` cmdlet. The default
is the current session on the local computer. For more information, see
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

Specifies the location of the virtual disk on the controller. If you don't specify a controller
location, the cmdlet returns all virtual disks attached to the specified controller.

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

Specifies the number of the controller where the virtual disk is attached. If you don't specify a
controller number, the cmdlet returns all virtual disks attached to the specified controller.

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

Specifies the type of controller used by the VM. If you don't specify a controller type, the cmdlet
uses the SCSI controller type, which is the only type supported at this time.

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

Specifies the drive controller object for which to retrieve virtual disk information. You can use
the [Get-VmScsiController](/powershell/module/hyper-v/get-vmscsicontroller) cmdlet to get the drive controller object.

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

Specifies the name of a virtual machine.

### Microsoft.HyperV.PowerShell.VirtualMachine[]

Specifies the virtual machine object for which to get directly attached virtual disks. You can use
the [Get-VM](/powershell/module/hyper-v/get-vm) cmdlet to get the virtual machine object.

### Microsoft.HyperV.PowerShell.VMDriveController[]

Specifies the drive controller objects for which to get directly attached virtual disks. You can use
the [Get-VmScsiController](/powershell/module/hyper-v/get-vmscsicontroller) cmdlet to get the drive
controller object.

## Outputs

### VMDirectVirtualDisk

Returns objects representing the virtual disks attached to the specified virtual machine.

## Notes

## Related links

- [Add-VMDirectVirtualDisk](Add-VMDirectVirtualDisk.md)

- [Remove-VMDirectVirtualDisk](Remove-VMDirectVirtualDisk.md)
