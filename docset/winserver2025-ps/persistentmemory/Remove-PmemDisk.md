---
description: The Remove-PmemDisk cmdlet removes persistent memory disks.
external help file: Microsoft.Storage.PersistentMemory.Management.Commands.dll-Help.xml
Module Name: PersistentMemory
ms.date: 09/24/2021
online version: https://learn.microsoft.com/powershell/module/persistentmemory/remove-pmemfisk?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-PmemDisk
---

# Remove-PmemDisk

## SYNOPSIS
Removes persistent memory disks.

## SYNTAX

### ByNumber
```
Remove-PmemDisk -DiskNumber <UInt32> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Simulated
```
Remove-PmemDisk [-Simulated] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-PmemDisk** cmdlet removes persistent memory disks.

You can use this cmdlet for troubleshooting.
If you remove a persistent memory disk, you lose all data on that disk.

You can specify a disk by number or remove disks from simulated persistent memory.

## EXAMPLES

### Example 1: Remove a persistent memory disk
```powershell
Remove-PmemDisk -DiskNumber 2
```

```output
This will remove the persistent memory disk(s) from the system and will result in data loss.
Remove the persistent memory disk(s)?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): Y
Removing the persistent memory disk. This may take a few moments.
```

This example removes a persistent memory disk.

### Example 1: Remove a disk in simulated persistent memory
```powershell
Remove-PmemDisk -Simulated
```

```output
This will remove the persistent memory disk(s) from the system and will result in data loss.
Remove the persistent memory disk(s)?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): Y
Removing the persistent memory disk. This may take a few moments.
```

This example removes the disks in simulated persistent memory.

## PARAMETERS

### -DiskNumber
Specifies the disk number of persistent memory disk to remove.

```yaml
Type: UInt32
Parameter Sets: ByNumber
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Force
Indicates that the command removes the disk without verification.
Removing a disk results in data loss.

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

### -Simulated
Indicates that the cmdlet removes simulated disks.

```yaml
Type: SwitchParameter
Parameter Sets: Simulated
Aliases:

Required: True
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

[Get-PmemDisk](Get-PmemDisk.md)

[New-PmemDisk](New-PmemDisk.md)
