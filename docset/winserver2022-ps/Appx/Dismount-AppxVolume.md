---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Windows.Appx.PackageManager.Commands.dll-Help.xml
Module Name: Appx
ms.date: 05/15/2023
online version: https://learn.microsoft.com/powershell/module/appx/dismount-appxvolume?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Dismount-AppxVolume
---

# Dismount-AppxVolume

## SYNOPSIS
Dismounts an appx volume.

## SYNTAX

```
Dismount-AppxVolume [-Volume] <AppxVolume[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

The `Dismount-AppxVolume` cmdlet dismounts an **AppxVolume**. After you dismount a volume, all
apps that are deployed to that target become inaccessible.

## EXAMPLES

### Example 1: Dismount a volume by using a path

```powershell
Dismount-AppxVolume -Volume E:\
```

This command dismounts a volume at the path `E:\`.

### Example 2: Dismount a volume by using an ID

```powershell
Dismount-AppxVolume -Volume {7e62a691-398e-4fbe-819a-64f1e407777a}
```

This command dismounts a volume that has the specified media ID.

## PARAMETERS

### -Volume

Specifies the **AppxVolume** object to dismount.

```yaml
Type: AppxVolume[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Confirm

Prompts you for confirmation before running the cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf

Shows what would happen if the cmdlet runs. The cmdlet isn't run.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-AppxVolume](./Add-AppxVolume.md)

[Get-AppxVolume](./Get-AppxVolume.md)

[Mount-AppxVolume](./Mount-AppxVolume.md)

[Remove-AppxVolume](./Remove-AppxVolume.md)
