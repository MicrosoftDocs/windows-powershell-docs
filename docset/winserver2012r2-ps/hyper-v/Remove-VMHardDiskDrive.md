---
external help file: Microsoft.HyperV.PowerShell.dll-Help.xml
Module Name: Hyper-V
ms.date: 10/30/2017
online version: https://learn.microsoft.com/powershell/module/hyper-v/remove-vmharddiskdrive?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-VMHardDiskDrive
---

# Remove-VMHardDiskDrive

## SYNOPSIS
Deletes a hard disk drive from a virtual machine.

## SYNTAX

### VMName (Default)
```
Remove-VMHardDiskDrive [-ComputerName <String[]>] [-VMName] <String> [-ControllerType] <ControllerType>
 [-ControllerNumber] <Int32> [-ControllerLocation] <Int32> [-Passthru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### VMHardDiskDrive
```
Remove-VMHardDiskDrive [-VMHardDiskDrive] <HardDiskDrive[]> [-Passthru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Remove-VMHardDiskDrive** cmdlet deletes a hard disk drive from a virtual machine.

## EXAMPLES

### Example 1
```
PS C:\>Remove-VMHardDiskDrive -VMName TestVM -ControllerType IDE -ControllerNumber 1 -ControllerLocation 0
```

Removes the virtual hard drive at IDE 1,0 on virtual machine TestVM.

### Example 2
```
PS C:\>Get-VMHardDiskDrive -VMName TestVM -ControllerType IDE -ControllerNumber 1 | Remove-VMHardDiskDrive
```

Removes all virtual hard drives on IDE controller 1 from virtual machine TestVM.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts from which the virtual hard disk drive is to be deleted.
NetBIOS names, IP addresses, and fully-qualified domain names are allowable.
The default is the local computer - use "localhost" or a dot (".") to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: VMName
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
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -ControllerLocation
Specifies the number of the location on the controller at which the virtual hard disk drive is to be deleted.
If not specified, the number of the first available location on the controller is used.

```yaml
Type: Int32
Parameter Sets: VMName
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ControllerNumber
Specifies the number of the controller from which the virtual hard disk drive is to be deleted.
If not specified, the first controller on which the specified **ControllerLocation** is available is used.

```yaml
Type: Int32
Parameter Sets: VMName
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ControllerType
Specifies the type of the controller where the virtual hard disk is to be deleted.
Allowed values are **IDE** and **SCSI**.

```yaml
Type: ControllerType
Parameter Sets: VMName
Aliases: 
Accepted values: IDE, SCSI, Floppy

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Passthru
Specifies that an object is to be passed through to be pipeline representing the virtual hard disk drive to be deleted.

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

### -VMHardDiskDrive
Specifies the virtual hard disk drive to be deleted.

```yaml
Type: HardDiskDrive[]
Parameter Sets: VMHardDiskDrive
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMName
Specifies the name of the virtual machine from which the virtual hard disk is to be deleted.

```yaml
Type: String
Parameter Sets: VMName
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.HyperV.PowerShell.HardDiskDrive[]

## OUTPUTS

###  
None by default; **Microsoft.HyperV.PowerShell.DriveController** if **-PassThru** is specified.

## NOTES

## RELATED LINKS

