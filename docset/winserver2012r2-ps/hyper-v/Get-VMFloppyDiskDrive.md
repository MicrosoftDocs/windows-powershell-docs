---
external help file: Microsoft.HyperV.PowerShell.dll-Help.xml
Module Name: Hyper-V
ms.date: 10/30/2017
online version: https://learn.microsoft.com/powershell/module/hyper-v/get-vmfloppydiskdrive?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-VMFloppyDiskDrive
---

# Get-VMFloppyDiskDrive

## SYNOPSIS
Gets the floppy disk drives of a virtual machine or snapshot.

## SYNTAX

### VMName (Default)
```
Get-VMFloppyDiskDrive [-ComputerName <String[]>] [-VMName] <String[]> [<CommonParameters>]
```

### VMSnapshot
```
Get-VMFloppyDiskDrive [-VMSnapshot] <VMSnapshot> [<CommonParameters>]
```

### VMObject
```
Get-VMFloppyDiskDrive [-VM] <VirtualMachine[]> [<CommonParameters>]
```

## DESCRIPTION
The **Get-VMFloppyDiskDrive** cmdlet gets the floppy disk drives of a virtual machine or snapshot.

## EXAMPLES

### Example 1
```
PS C:\>Get-VMFloppyDiskDrive TestVM
```

Gets the floppy disk drive for virtual machine TestVM.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts on which floppy disk drives are to be retrieved.
NetBIOS names, IP addresses, and fully-qualified domain names are allowable.
The default is the local computer - use "localhost" or a dot (".") to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: VMName
Aliases: 

Required: False
Position: Named
Default value: .
Accept pipeline input: False
Accept wildcard characters: False
```

### -VM
Specifies the virtual machine whose floppy disk drives are to be retrieved.

```yaml
Type: VirtualMachine[]
Parameter Sets: VMObject
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMName
Specifies the name of the virtual machine whose floppy disk drives are to be retrieved.

```yaml
Type: String[]
Parameter Sets: VMName
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMSnapshot
Specifies the snapshot whose floppy disk drives are to be retrieved.

```yaml
Type: VMSnapshot
Parameter Sets: VMSnapshot
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.HyperV.PowerShell.FloppyDiskDrive

## NOTES

## RELATED LINKS

