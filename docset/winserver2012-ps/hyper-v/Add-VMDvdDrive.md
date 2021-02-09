---
external help file: Hyper-V_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Add-VMDvdDrive

## SYNOPSIS
Adds a DVD drive to a virtual machine.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Add-VMDvdDrive [-VMName] <String[]> [[-ControllerNumber] <Int32>] [[-ControllerLocation] <Int32>]
 [[-Path] <String>] [-AllowUnverifiedPaths] [-ComputerName <String[]>] [-Passthru] [-ResourcePoolName <String>]
 [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Add-VMDvdDrive [-VM] <VirtualMachine[]> [[-ControllerNumber] <Int32>] [[-ControllerLocation] <Int32>]
 [[-Path] <String>] [-AllowUnverifiedPaths] [-Passthru] [-ResourcePoolName <String>] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_3
```
Add-VMDvdDrive [-VMDriveController] <VMDriveController[]> [[-ControllerLocation] <Int32>] [[-Path] <String>]
 [-AllowUnverifiedPaths] [-Passthru] [-ResourcePoolName <String>] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Add-VMDvdDrive** cmdlet adds a DVD drive to a virtual machine.

## EXAMPLES

### Example 1
```
PS C:\>Add-VMDvdDrive -VMName Test -Path D:\ISOs\disc1.iso
```

This example adds a virtual DVD drive using file D:\ISOs\disc1.iso to virtual machine Test.

### Example 2
```
PS C:\>Get-VM Test | Add-VMDvdDrive -ControllerNumber 1
```

This example adds a virtual DVD drive using controller number 1 to virtual machine Test.

### Example 3
```
PS C:\>Get-VMIdeController -VMName Test | Add-VMDvdDrive -Path E:\
```

This example adds virtual DVD drives using the IDE controllers from virtual machine Test.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-v hosts on which the DVD drive is to be added.
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
Specifies the number of the location on the controller at which the DVD drive is to be added.
If not specified, the number of the first available location on the controller is used.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ControllerNumber
Specifies the number of the controller to which the DVD drive is to be added.
If not specified, the first IDE controller on which the specified **ControllerLocation** is available is used.

```yaml
Type: Int32
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Passthru
Passes the added **Microsoft.Virtualization.Powershell.DvdDrive** through to the pipeline.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path
Specifies the full path to the virtual hard disk file or physical hard disk volume for the added DVD drive.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 5
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourcePoolName
Specifies the friendly name of the ISO resource pool to which this DVD drive is to be associated.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VM
Specifies the virtual machine to which the DVD drive is to be added.

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
Specifies the drive controller to which the DVD drive is to be added.

```yaml
Type: VMDriveController[]
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMName
Specifies the name of the virtual machine to which the DVD drive is to be added.

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

### -AllowUnverifiedPaths
Specifies that no error is to be thrown if the specified path is not verified as accessible by the cluster.
This parameter is applicable to clustered virtual machines.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

### Microsoft.HyperV.PowerShell.VMDriveController[]

### Microsoft.HyperV.PowerShell.VirtualMachine[]

## OUTPUTS

### Microsoft.Virtualization.Powershell.DvdDrive

## NOTES

## RELATED LINKS



