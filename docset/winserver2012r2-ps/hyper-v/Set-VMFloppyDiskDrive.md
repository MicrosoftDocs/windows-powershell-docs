---
external help file: Microsoft.HyperV.PowerShell.dll-Help.xml
Module Name: Hyper-V
online version: 
schema: 2.0.0
title: Set-VMFloppyDiskDrive
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: E12B0A47-7B67-4DCA-BA16-3B581421E1AD
---

# Set-VMFloppyDiskDrive

## SYNOPSIS
Configures a virtual floppy disk drive.

## SYNTAX

### VMName (Default)
```
Set-VMFloppyDiskDrive [[-Path] <String>] [-ResourcePoolName <String>] [-Passthru] [-ComputerName <String[]>]
 [-VMName] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### VMFloppyDiskDrive
```
Set-VMFloppyDiskDrive [-VMFloppyDiskDrive] <VMFloppyDiskDrive[]> [[-Path] <String>]
 [-ResourcePoolName <String>] [-Passthru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### VMObject
```
Set-VMFloppyDiskDrive [[-Path] <String>] [-ResourcePoolName <String>] [-Passthru] [-VM] <VirtualMachine[]>
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-VMFloppyDiskDrive** cmdlet configures a virtual floppy disk drive.

## EXAMPLES

### Example 1
```
PS C:\>Set-VMFloppyDiskDrive TestVM C:\Test.vfd
```

Connect C:\Test.vfd to the virtual floppy disk of virtual machine TestVM.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts on which the virtual floppy disk drive is to be configured.
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

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Passthru
Specifies that a **Microsoft.HyperV.PowerShell.FloppyDiskDrive** object is to be passed through to the pipeline representing the virtual floppy disk drive to be configured.

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
Specifies the path to the virtual floppy drive file.
If specified as **$null**, the drive is set to contain no media.

```yaml
Type: String
Parameter Sets: (All)
Aliases: FullName

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourcePoolName
Specifies the name of the virtual floppy disk resource pool to use for this virtual floppy disk.

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
Specifies the virtual machine in which the virtual floppy disk drive is to be configured.

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

### -VMFloppyDiskDrive
Specifies the virtual floppy disk drive to be configured.

```yaml
Type: VMFloppyDiskDrive[]
Parameter Sets: VMFloppyDiskDrive
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMName
Specifies the name of the virtual machine on which the virtual floppy disk drive is to be configured.

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

### -WhatIf
Shows what would happen if the cmdlet runs. The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

