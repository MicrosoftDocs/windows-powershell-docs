---
external help file: VMDirectStorage-help.xml
Module Name: VMDirectStorage
ms.date: 03/25/2025
online version: https://learn.microsoft.com/powershell/module/vmdirectstorage/remove-vmdirectvirtualdisk?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-VMDirectVirtualDisk
ai-usage: ai-generated
---

# Remove-VMDirectVirtualDisk

## SYNOPSIS

Detaches a Storage Spaces Direct virtual disk from a virtual machine.

## SYNTAX

### ByVMName

```
Remove-VMDirectVirtualDisk [-VMName] <String> [-CimSession <CimSession[]>] [-ControllerType] <ControllerType>
 [-ControllerNumber] <Int32> [-ControllerLocation] <Int32> [<CommonParameters>]
```

### ByVirtualDisk

```
Remove-VMDirectVirtualDisk [-VirtualDisk] <VMDirectVirtualDisk[]> [<CommonParameters>]
```

## DESCRIPTION

The **Remove-VMDirectVirtualDisk** cmdlet detaches a Storage Spaces Direct virtual disk from a virtual machine. This operation ensures that the virtual disk is no longer accessible by the VM.

## EXAMPLES

### Example 1

```powershell
$parameters = @{
    VMName            = "VM1"
    ControllerType    = "SCSI"
    ControllerNumber  = 0
    ControllerLocation = 1
}
Remove-VMDirectVirtualDisk @parameters
```

This command detaches the virtual disk located at controller 0, location 1, from the virtual machine named "VM1".

## PARAMETERS

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

Specifies the location of the virtual disk on the controller.

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

Specifies the number of the controller where the virtual disk is attached.

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

Specifies the type of controller. Only SCSI is supported.

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

Specifies the virtual disk object to detach.

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

Specifies the name of the virtual machine from which the virtual disk will be detached.

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

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

Specifies the name of the virtual machine.

### VMDirectVirtualDisk[]

Specifies the virtual disk objects to be detached.

## OUTPUTS

### System.Object

Returns an object representing the result of the operation.

## NOTES

## RELATED LINKS

[Add-VMDirectVirtualDisk](Add-VMDirectVirtualDisk.md)

[Get-VMDirectVirtualDisk](Get-VMDirectVirtualDisk.md)
