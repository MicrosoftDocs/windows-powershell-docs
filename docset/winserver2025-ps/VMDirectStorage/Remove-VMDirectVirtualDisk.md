---
external help file: VMDirectStorage-help.xml
Module Name: VMDirectStorage
ms.date: 03/28/2025
online version: https://learn.microsoft.com/powershell/module/vmdirectstorage/remove-vmdirectvirtualdisk?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-VMDirectVirtualDisk
ai-usage: ai-generated
---

# Remove-VMDirectVirtualDisk

## Synopsis

Detaches a Storage Spaces Direct virtual disk from a virtual machine.

## Syntax

### ByVMName

```
Remove-VMDirectVirtualDisk [-VMName] <String> [-CimSession <CimSession[]>] [-ControllerType] <ControllerType>
 [-ControllerNumber] <Int32> [-ControllerLocation] <Int32> [<CommonParameters>]
```

### ByVirtualDisk

```
Remove-VMDirectVirtualDisk [-VirtualDisk] <VMDirectVirtualDisk[]> [<CommonParameters>]
```

## Description

The **Remove-VMDirectVirtualDisk** cmdlet detaches a Storage Spaces Direct virtual disk from a
virtual machine. This operation ensures that the virtual disk is no longer accessible by the VM.

## Examples

### Example 1: Detach a virtual disk by specifying VM name and controller details

This command detaches the virtual disk located at controller 0, location 1, from the virtual machine
named `VM1`.

```powershell
$parameters = @{
    VMName            = "VM1"
    ControllerType    = "SCSI"
    ControllerNumber  = 0
    ControllerLocation = 1
}
Remove-VMDirectVirtualDisk @parameters
```

### Example 2: Detach a virtual disk by using the virtual disk object

This example gets all of the virtual disks directly attached to `VM1` on `Cluster01` and then removes them.

```powershell
$VmDirectDisk = Get-VMDirectVirtualDisk -VMName "VM1" -CimSession "Cluster01"
Remove-VMDirectVirtualDisk -VirtualDisk $VmDirectDisk
```

## Parameters

### -CimSession

Runs the command using the specified CIM session. Enter a variable that contains the CIM session, or
a command that creates or gets the CIM session, such as `New-CimSession` or `Get-CimSession`. For
more information, see
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

Specifies the location on the controller of the virtual disk to remove. If you don't specify a
controller location, the cmdlet removes all directly virtual disks attached to the specified
controller.

```yaml
Type: System.Int32
Parameter Sets: ByVMName
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ControllerNumber

Specifies the number of the controller where the virtual disk is attached. If you don't specify a
controller number, the cmdlet removes all directly virtual disks on the specified controller.

```yaml
Type: System.Int32
Parameter Sets: ByVMName
Aliases:

Required: True
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
Parameter Sets: ByVMName
Aliases:
Accepted values: SCSI

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualDisk

Specifies the virtual disk object to remove.

```yaml
Type: VMDirectVirtualDisk[]
Parameter Sets: ByVirtualDisk
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMName

Specifies the name of the virtual machine from which the directly attached virtual disk will be removed.

```yaml
Type: System.String
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

### System.String

Specifies the name of the virtual machine.

### VMDirectVirtualDisk[]

Specifies the virtual disk objects to be removed. You can get the virtual disk object by using the
[Get-VMDirectVirtualDisk](Get-VMDirectVirtualDisk.md) cmdlet.

## Outputs

### None

This cmdlet returns no output of its own.

## Notes

## Related links

- [Add-VMDirectVirtualDisk](Add-VMDirectVirtualDisk.md)

- [Get-VMDirectVirtualDisk](Get-VMDirectVirtualDisk.md)
