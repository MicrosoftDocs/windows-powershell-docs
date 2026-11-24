---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Windows.Appx.PackageManager.Commands.dll-Help.xml
Module Name: Appx
ms.date: 05/15/2023
online version: https://learn.microsoft.com/powershell/module/appx/add-appxvolume?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-AppxVolume
---

# Add-AppxVolume

## SYNOPSIS
Adds an appx volume to the Package Manager.

## SYNTAX

```
Add-AppxVolume [-Path] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

The `Add-AppxVolume` cmdlet adds an **AppxVolume** for the Package Manager to advertise. After you
add a volume, Appx deployment operations can use that volume as a target. This cmdlet returns the
volume that it adds. Note, the **Path** parameter must be specified as a drive letter followed by
`WindowsApps` as the directory. Not using this format could lead to inconsistent behavior in the
application model subsystems or the volume itself. For more information, see the examples section.

## EXAMPLES

### Example 1: Add a volume

```powershell
Add-AppxVolume -Path "E:\WindowsApps"
```

This command adds the volume `E:\WindowsApps` to Package Manager.

## PARAMETERS

### -Path

Specifies the path of the mount point of the volume that this cmdlet adds.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: PSPath

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

### Microsoft.Appx.PackageManager.Commands.AppxVolume

This cmdlet returns the **AppxVolume** object that it adds.

## NOTES

## RELATED LINKS

[Dismount-AppxVolume](./Dismount-AppxVolume.md)

[Get-AppxVolume](./Get-AppxVolume.md)

[Mount-AppxVolume](./Mount-AppxVolume.md)

[Remove-AppxVolume](./Remove-AppxVolume.md)
