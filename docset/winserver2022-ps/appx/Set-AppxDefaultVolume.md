---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Windows.Appx.PackageManager.Commands.dll-Help.xml
Module Name: Appx
ms.date: 05/15/2023
online version: https://learn.microsoft.com/powershell/module/appx/set-appxdefaultvolume?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-AppxDefaultVolume
---

# Set-AppxDefaultVolume

## SYNOPSIS
Specifies a default appx volume.

## SYNTAX

```
Set-AppxDefaultVolume [-Volume] <AppxVolume> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

The `Set-AppxDefaultVolume` cmdlet specifies a default **AppxVolume**. The default **AppxVolume**
is the default target for all deployment operations on the computer. Deployment operations can
specify a different non-default target volume.

## EXAMPLES

### Example 1: Set a default volume by using a path

```powershell
Set-AppxDefaultVolume -Volume F:\
```

This command sets the default volume to be the volume `F:\`.

### Example 2: Set a default volume by using an ID

```powershell
Set-AppxDefaultVolume -Volume {ef23c8d6-b13c-4c4c-ae3b-7d5a162de9b9}
```

This command sets the default volume to be the one that has the specified media ID.

## PARAMETERS

### -Volume

Specifies the path a volume. This cmdlet sets the volume that this parameter specifies to be the
default deployment target for the computer.

```yaml
Type: AppxVolume
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

[Get-AppxDefaultVolume](./Get-AppxDefaultVolume.md)
