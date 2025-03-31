---
external help file: VMDirectStorage-help.xml
Module Name: VMDirectStorage
ms.date: 03/28/2025
online version: https://learn.microsoft.com/powershell/module/vmdirectstorage/add-vmdirectvirtualdisk?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-VMDirectVirtualDisk
ai-usage: ai-generated
---

# Add-VMDirectVirtualDisk

## Synopsis

Attaches a Storage Spaces Direct virtual disk to a virtual machine.

## Syntax

### ByVMName

```
Add-VMDirectVirtualDisk [-VMName] <String[]> [-CimSession <CimSession[]>] [[-ControllerType] <ControllerType>]
 [[-ControllerNumber] <Int32>] [-ControllerLocation <Int32>] [-VirtualDiskUniqueId <String>]
 [<CommonParameters>]
```

### ByVM

```
Add-VMDirectVirtualDisk [-VM] <VirtualMachine[]> [[-ControllerType] <ControllerType>]
 [[-ControllerNumber] <Int32>] [-ControllerLocation <Int32>] [-VirtualDiskUniqueId <String>]
 [<CommonParameters>]
```

### ByVMDriveController

```
Add-VMDirectVirtualDisk [-VMDriveController] <VMDriveController> [-ControllerLocation <Int32>]
 [-VirtualDiskUniqueId <String>] [<CommonParameters>]
```

## Description

The **Add-VMDirectVirtualDisk** cmdlet attaches a Storage Spaces Direct virtual disk to a virtual
machine. This enables high-performance storage configurations by directly connecting the virtual
disk to the VM.

## Examples

### Example 1: Attach a virtual disk by specifying VM name and controller details

This example attaches the virtual disk with the unique ID "111BBE22FD037E4EB87F366648FBF111" to the
virtual machine named "VM1" at controller 0, location 1.

```powershell
$parameters = @{
    VMName             = "VM1"
    ControllerType     = "SCSI"
    ControllerNumber   = 0
    ControllerLocation = 1
    VirtualDiskUniqueId = "111BBE22FD037E4EB87F366648FBF111"
}

Add-VMDirectVirtualDisk @parameters
```

### Example 2: Attach a virtual disk by using a virtual disk object

This example gets the Storage Spaces Direct virtual disk object named "Volume01" and the VM object
named "VM1", and then directly attaches the disk to the VM.

```powershell
$virtualDisk = Get-VirtualDisk -Friendlyname "Volume01"
$vm = Get-VM -Name "VM1"

Add-VMDirectVirtualDisk -VM $vm -VirtualDiskUniqueId $virtualDisk.UniqueId
```

## Parameters

### -CimSession

Specifies the CIM session to use for the operation. This is useful for managing remote systems.

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

Specifies the location on the controller where the virtual disk will be attached.

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

Specifies the number of the controller where the virtual disk will be attached.

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

### -VirtualDiskUniqueId

Specifies the unique ID of the virtual disk to attach.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VM

Specifies the virtual machine object to which the virtual disk will be attached.

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

Specifies the drive controller object to which the virtual disk will be attached.

```yaml
Type: Microsoft.HyperV.PowerShell.VMDriveController
Parameter Sets: ByVMDriveController
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMName

Specifies the name of the virtual machine to which the virtual disk will be attached.

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

### Microsoft.HyperV.PowerShell.VMDriveController

Specifies drive controller objects.

## Outputs

### System.Object

Returns an object representing the result of the operation.

## Notes

## Related links

- [Get-VMDirectVirtualDisk](Get-VMDirectVirtualDisk.md)

- [Remove-VMDirectVirtualDisk](Remove-VMDirectVirtualDisk.md)
