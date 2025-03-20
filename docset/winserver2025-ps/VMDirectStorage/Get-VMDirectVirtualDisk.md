---
external help file: VMDirectStorage-help.xml
Module Name: VMDirectStorage
ms.date: 3/20/2025
online version: https://learn.microsoft.com/powershell/module/vmdirectstorage/get-vmdirectvirtualdisk?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-VMDirectVirtualDisk
ai-usage: ai-generated
---

# Get-VMDirectVirtualDisk

## SYNOPSIS

Retrieves direct-attached virtual disks from Hyper-V virtual machines.

## SYNTAX

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

## DESCRIPTION

The `Get-VMDirectVirtualDisk` cmdlet retrieves information about direct-attached virtual disks configured on Hyper-V virtual machines. You can filter results by virtual machine name, controller type, number, or location.

## EXAMPLES

### Example 1

```powershell
PS C:\> Get-VMDirectVirtualDisk -VMName "VM01"
```

This command retrieves all direct-attached virtual disks configured on the virtual machine named VM01.

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

Filters results by the location on the controller.

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

Filters results by the controller number.

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

Filters results by the controller type. Currently, only SCSI is supported.

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

Specifies the virtual machine object from which to retrieve virtual disks.

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

Specifies the VM drive controller object from which to retrieve virtual disks.

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

Specifies the name of the virtual machine from which to retrieve virtual disks.

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

Supports common parameters. See [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String[]

Accepts virtual machine names as input.

### Microsoft.HyperV.PowerShell.VirtualMachine[]

Accepts virtual machine objects as input.

### Microsoft.HyperV.PowerShell.VMDriveController[]

Accepts VM drive controller objects as input.

## OUTPUTS

### VMDirectVirtualDisk[]

Returns objects representing direct-attached virtual disks.

## NOTES

None.

## RELATED LINKS

[Add-VMDirectVirtualDisk](Add-VMDirectVirtualDisk.md)  
[Remove-VMDirectVirtualDisk](Remove-VMDirectVirtualDisk.md)
