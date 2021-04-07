---
author: Kateyanne
description: 
external help file: Microsoft.HyperV.PowerShell.dll-Help.xml
manager: jasgro
Module Name: Hyper-V
ms.author: v-kaunu
ms.date: 10/30/2017
ms.prod: powershell
ms.reviewer: brianlic
ms.topic: reference
online version: https://docs.microsoft.com/powershell/module/hyper-v/test-vhd?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Test-VHD
---

# Test-VHD

## SYNOPSIS
Tests a virtual hard disk for any problems that would make it unusable.

## SYNTAX

### ExistingVHD (Default)
```
Test-VHD [-Path] <String[]> [-ComputerName <String[]>] [<CommonParameters>]
```

### SharedDisk
```
Test-VHD [-Path] <String[]> [-SupportPersistentReservations] [-ComputerName <String[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Test-VHD** cmdlet tests a virtual hard disk for any problems that would make it unusable.

## EXAMPLES

### Example 1
```
PS C:\>Test-VHD -Path Diff2.vhdx
```

Tests whether the virtual hard disk chain is in a usable state that starts with the virtual hard disk associated with Diff2.vhdx.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts on which the virtual hard disk is to be tested.
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

### -Path
Specifies the path to the virtual hard disk file of the virtual hard disk to be tested.
If a filename or relative path is specified, the new virtual hard disk path is calculated relative to the current working directory.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: FullName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -SupportPersistentReservations
Indicates that the cmdlet tests for SCSI persistent reservation support semantics.
Specify this parameter to test whether a virtual hard disk or path supports shared virtual disks.

```yaml
Type: SwitchParameter
Parameter Sets: SharedDisk
Aliases: ShareVirtualDisk

Required: True
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

