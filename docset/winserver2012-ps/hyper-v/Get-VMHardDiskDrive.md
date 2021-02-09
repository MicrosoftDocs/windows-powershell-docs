---
external help file: Hyper-V_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Get-VMHardDiskDrive

## SYNOPSIS
Gets the virtual hard disk drives attached to one or more virtual machines.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-VMHardDiskDrive [-VMName] <String[]> [-ComputerName <String[]>] [-ControllerLocation <Int32>]
 [-ControllerNumber <Int32>] [-ControllerType <ControllerType>]
```

### UNNAMED_PARAMETER_SET_2
```
Get-VMHardDiskDrive [-VM] <VirtualMachine[]> [-ControllerLocation <Int32>] [-ControllerNumber <Int32>]
 [-ControllerType <ControllerType>]
```

### UNNAMED_PARAMETER_SET_3
```
Get-VMHardDiskDrive [-VMSnapshot] <VMSnapshot> [-ControllerLocation <Int32>] [-ControllerNumber <Int32>]
 [-ControllerType <ControllerType>]
```

### UNNAMED_PARAMETER_SET_4
```
Get-VMHardDiskDrive [-VMDriveController] <VMDriveController[]> [-ControllerLocation <Int32>]
```

## DESCRIPTION
The **Get-VMHardDiskDrive** cmdlet gets the virtual hard disk drives attached to one or more virtual machines.

## EXAMPLES

### Example 1
```
PS C:\>Get-VMHardDiskDrive -VMName TestVM
```

Gets the virtual hard drives from virtual machine TestVM.

### Example 2
```
PS C:\>Get-VM -Name TestVM | Get-VMHardDiskDrive -ControllerType IDE -ControllerNumber 1
```

Gets the virtual hard drives from IDE controller 1 of virtual machine TestVM.

### Example 3
```
PS C:\>Get-VMIdeController -VMName TestVM -ControllerNumber 1 -ComputerName Development | Get-VMHardDiskDrive
```

Gets the virtual hard drives from IDE controller 1 of virtual machine TestVM located on Hyper-V host Development.

### Example 4
```
PS C:\>Get-VMSnapshot -VMName Test -Name 'Before applying updates' | Get-VMHardDrive
```

Gets the virtual hard drives from snapshot Before applying updates of virtual machine TestVM.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts from which the virtual hard disk drives are to be retrieved.
NetBIOS names, IP addresses, and fully-qualified domain names are allowable.
The default is the local computer - use "localhost" or a dot (".") to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: .
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
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_3
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ControllerType
Specifies the type of the controller from which the virtual hard disk drives are to be retrieved.
Allowed values are **IDE** and **SCSI**.

```yaml
Type: ControllerType
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_3
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
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMDriveController
Specifies the drive controller from which the virtual hard disk drives are to be retrieved.

```yaml
Type: VMDriveController[]
Parameter Sets: UNNAMED_PARAMETER_SET_4
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMName
Specifies the name of the virtual machine from which the virtual hard disks drives are to be retrieved.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMSnapshot
Specifies the snapshot from which the virtual hard disk drives are to be retrieved.

```yaml
Type: VMSnapshot
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

## INPUTS

### Microsoft.HyperV.PowerShell.ControllerType

### Microsoft.HyperV.PowerShell.VMSnapshot

### Microsoft.HyperV.PowerShell.VMDriveController[]

### Microsoft.HyperV.PowerShell.VirtualMachine[]

## OUTPUTS

### Microsoft.Virtualization.Powershell.HardDiskDrive

## NOTES

## RELATED LINKS



