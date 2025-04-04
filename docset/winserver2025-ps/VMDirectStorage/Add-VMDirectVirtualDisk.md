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

Directly attaches a Storage Spaces Direct virtual disk to a virtual machine.

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

The **Add-VMDirectVirtualDisk** cmdlet directly attaches a Storage Spaces Direct virtual disk to a
virtual machine. This enables high-performance storage configurations by directly connecting the
virtual disk to the VM.

## Examples

### Example 1: Attach a virtual disk by using a virtual disk object

This example gets the Storage Spaces Direct virtual disk object named `Volume01` and the VM object
named `VM1` on `Cluster01`, and then directly attaches the disk to the VM, using the first available
controller and controller location.

```powershell
$VirtualDisk = Get-VirtualDisk -FriendlyName "Volume01" -CimSession "Cluster01"
$vm = Get-VM -Name "VM1" -CimSession "Cluster01"

Add-VMDirectVirtualDisk -VM $vm -VirtualDiskUniqueId $VirtualDisk.UniqueId
```

### Example 2: Attach a virtual disk by specifying VM name and controller details

This example attaches the virtual disk with the unique ID `111BBE22FD037E4EB87F366648FBF111` to the
virtual machine named `VM1` at controller 0, location 1.

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

### Example 3: Attach multiple virtual disks to a VM

This example retrieves all virtual disks with names starting with `Volume0` from the cluster named
`Cluster01` and attaches them to the virtual machine named `VM1`.

```powershell
$VirtualDisks = Get-VirtualDisk -FriendlyName "Volume0*" -CimSession "Cluster01"
$vm = Get-VM -Name "VM1" -CimSession "Cluster01"

foreach ($diskID in $virtualdisks) {
 Add-VMDirectVirtualDisk -VM $vm -VirtualDiskUniqueId $diskID.UniqueID
}
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

Specifies the location on the controller where the virtual disk will be attached. If you don't
specify a controller location, the cmdlet uses the first available location.

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

Specifies the number of the controller where the virtual disk will be attached. If you don't specify
a controller number, the cmdlet uses the first available controller.

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

### -VirtualDiskUniqueId

Specifies the unique ID of the Storage Spaces virtual disk to attach. For example,
`111BBE22-FD03-7E4E-B87F-366648FBF111`.

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

Specifies a virtual machine object to which the virtual disk will be attached.

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

Specifies the name of the virtual machine to which the virtual disk will be directly attached.

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

Specifies a virtual machine object to which the virtual disk will be attached. You can use the
[Get-VM](/powershell/module/hyper-v/get-vm) cmdlet to get the virtual machine object.

### Microsoft.HyperV.PowerShell.VMDriveController

Specifies a drive controller object to which the virtual disk will be attached. You can use
the [Get-VmScsiController](/powershell/module/hyper-v/get-vmscsicontroller) cmdlet to get the drive
controller object.

## Outputs

### None

This cmdlet returns no output of its own.

## Notes

## Related links

- [Get-VMDirectVirtualDisk](Get-VMDirectVirtualDisk.md)

- [Remove-VMDirectVirtualDisk](Remove-VMDirectVirtualDisk.md)
