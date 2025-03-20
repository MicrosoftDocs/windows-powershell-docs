---
external help file: VMDirectStorage-help.xml
Module Name: VMDirectStorage
ms.date: 3/20/2025
online version: https://learn.microsoft.com/powershell/module/vmdirectstorage/remove-vmdirectvirtualdisk?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-VMDirectVirtualDisk
ai-usage: ai-generated
---

# Remove-VMDirectVirtualDisk

## SYNOPSIS

Removes a direct-attached virtual disk from a Hyper-V virtual machine.

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

The `Remove-VMDirectVirtualDisk` cmdlet detaches a direct-attached virtual disk from a Hyper-V virtual machine. This cmdlet can be used to manage storage configurations by removing virtual disks that are no longer required or need to be reconfigured.

## EXAMPLES

### Example 1

```powershell
PS C:\> Remove-VMDirectVirtualDisk -VMName "VM01" -ControllerType SCSI -ControllerNumber 0 -ControllerLocation 1
```

This command removes the virtual disk attached to the SCSI controller 0 at location 1 on the virtual machine named VM01.

### Example 2

```powershell
PS C:\> $disk = Get-VMDirectVirtualDisk -VMName "VM01"
PS C:\> Remove-VMDirectVirtualDisk -VirtualDisk $disk
```

This command retrieves all direct-attached virtual disks on the virtual machine named VM01 and removes them.

## PARAMETERS

### -CimSession

Specifies the CIM session to use for remote management.

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

Specifies the location on the controller where the virtual disk is attached. Valid values are from 0 to 63.

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

Specifies the number of the controller from which the virtual disk is removed.

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

Specifies the type of controller. Currently, only SCSI is supported.

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

Specifies the direct-attached virtual disk object to remove.

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

Specifies the name of the virtual machine from which the virtual disk is removed.

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

Accepts the name of the virtual machine as input.

### VMDirectVirtualDisk[]

Accepts direct-attached virtual disk objects as input.

## OUTPUTS

### System.Object

Returns an object representing the removed virtual disk.

## NOTES

Removing a direct-attached virtual disk does not delete the underlying disk file. The disk remains available for reattachment or other operations.

## RELATED LINKS

[Add-VMDirectVirtualDisk](Add-VMDirectVirtualDisk.md)  
[Get-VMDirectVirtualDisk](Get-VMDirectVirtualDisk.md)
