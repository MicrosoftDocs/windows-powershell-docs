---
external help file: Microsoft.HyperV.PowerShell.dll-Help.xml
Module Name: Hyper-V
online version: 
schema: 2.0.0
title: Dismount-VHD
ms.author: kenwith
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: kenwith
manager: jasgro
ms.date: 2017-10-30
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: C066F232-F87A-4EA0-AD33-D036A1E80083
---

# Dismount-VHD

## SYNOPSIS
Dismounts a virtual hard disk.

## SYNTAX

### Path (Default)
```
Dismount-VHD [-Path] <String[]> [-Passthru] [-ComputerName <String[]>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### Disk
```
Dismount-VHD [-DiskNumber] <UInt32> [-Passthru] [-ComputerName <String[]>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Dismount-VHD** cmdlet dismounts a virtual hard disk.

## EXAMPLES

### Example 1
```
PS C:\>Dismount-VHD -Path c:\test\testvhdx.vhdx
```

Dismounts an attached virtual hard disk where the path to the virtual hard disk file path is c:\test\testvhdx.vhdx.

### Example 2
```
PS C:\>Dismount-VHD -DiskNumber 6
```

Dismounts the attached virtual hard disk image with disk number 6.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts on which a virtual hard disk is to be dismounted.
NetBIOS names, IP addresses, and fully-qualified domain names are allowable.
The default is the local computer - use "localhost" or a dot (".") to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: (All)
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
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -DiskNumber
Specifies the disk number of the virtual hard disk to be dismounted.

```yaml
Type: UInt32
Parameter Sets: Disk
Aliases: Number

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Passthru
Specifies that an object is to be passed through to the pipeline representing the virtual hard disk to be dismounted.

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
Specifies one or more virtual hard disk files for which the corresponding virtual hard disks are to be dismounted.

```yaml
Type: String[]
Parameter Sets: Path
Aliases: FullName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

