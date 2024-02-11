---
description: The Remove-PmemDedicatedMemory cmdlet gets dedicated persistent memory.
external help file: Microsoft.Storage.PersistentMemory.Management.Commands.dll-Help.xml
Module Name: PersistentMemory
ms.date: 09/24/2021
online version: https://learn.microsoft.com/powershell/module/persistentmemory/remove-pmemdedicatedmemory?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-PmemDedicatedMemory
---

# Remove-PmemDedicatedMemory

## SYNOPSIS
Gets dedicated persistent memory.

## SYNTAX

```
Remove-PmemDedicatedMemory -DeviceNumber <UInt32> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-PmemDedicatedMemory** cmdlet gets dedicated persistent memory.

## EXAMPLES

### Example 1: Remove dedicated persistent memory
```powershell
Remove-PmemDedicatedMemory -DeviceNumber 1
```

This example removes the specified dedicated persistent memory.

## PARAMETERS

### -DeviceNumber
Specifies the device number for the physical device.
The cmdlet removes dedicated memory for that device.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Force
Indicates that the command removes the  dedicated persistent memory without verification.
Removing memory results in data loss.

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
Aliases: cf

Required: False
Position: Named
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
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.UInt32

## OUTPUTS

### System.Object
## NOTES

## RELATED LINKS

[Get-PmemDedicatedMemory](Get-PmemDedicatedMemory.md)

[New-PmemDedicatedMemory](New-PmemDedicatedMemory.md)
