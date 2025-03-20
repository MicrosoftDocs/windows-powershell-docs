---
external help file: VMDirectStorage-help.xml
Module Name: VMDirectStorage
ms.date: 3/20/2025
online version: https://learn.microsoft.com/powershell/module/vmdirectstorage/add-vmdirectvirtualdisk?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-VMDirectVirtualDisk
ai-usage: ai-generated
---

# Add-VMDirectVirtualDisk

## SYNOPSIS

Adds a direct-attached virtual disk to a Hyper-V virtual machine.

## SYNTAX

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

## DESCRIPTION

The `Add-VMDirectVirtualDisk` cmdlet attaches an existing virtual disk directly to a Hyper-V virtual machine. Direct-attached virtual disks provide improved storage performance by bypassing traditional virtual storage layers.

## EXAMPLES

### Example 1

```powershell
PS C:\> Add-VMDirectVirtualDisk -VMName "VM01" -ControllerType SCSI -ControllerNumber 0 -ControllerLocation 1 -VirtualDiskUniqueId "12345678-ABCD-1234-ABCD-1234567890AB"
```

This command attaches a virtual disk identified by its unique ID directly to the SCSI controller 0 at location 1 on the virtual machine named VM01.

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
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ControllerNumber

Specifies the number of the controller to which the virtual disk is attached.

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

Specifies the type of controller. Currently, only SCSI is supported.

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

Specifies the unique identifier of the virtual disk to attach.

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

Specifies the virtual machine object to which the virtual disk is attached.

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

Specifies the VM drive controller object to which the virtual disk is attached.

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

Specifies the name of the virtual machine to which the virtual disk is attached.

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

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String[]

Accepts virtual machine names as input.

### Microsoft.HyperV.PowerShell.VirtualMachine[]

Accepts virtual machine objects as input.

### Microsoft.HyperV.PowerShell.VMDriveController

Accepts VM drive controller objects as input.

## OUTPUTS

### System.Object

Returns an object representing the attached virtual disk.

## NOTES

Direct-attached virtual disks require compatible hardware and configuration.

## RELATED LINKS

[Get-VMDirectVirtualDisk](Get-VMDirectVirtualDisk.md)  
[Remove-VMDirectVirtualDisk](Remove-VMDirectVirtualDisk.md)
