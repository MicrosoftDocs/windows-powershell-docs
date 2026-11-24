---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MultiPointVdi.dll-Help.xml
Module Name: MultiPointVdi
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/multipointvdi/enable-wmsvirtualdesktoprole?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-WmsVirtualDesktopRole
---

# Enable-WmsVirtualDesktopRole

## SYNOPSIS
Installs the Hyper-V virtual desktop role and customizes it for use with MultiPoint services.

## SYNTAX

```
Enable-WmsVirtualDesktopRole [-Restart] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Enable-WmsVirtualDesktopRole** cmdlet installs the virtual desktop Hyper-V role if it isn't already installed, and optionally restarts the computer to apply the change.

## EXAMPLES

### Example 1: Install the Hyper-V virtual desktop role
```
PS C:\> Enable-WmsVirtualDesktopRole -Restart
```

This command installs the Hyper-V virtual desktop role and reboots the computer to apply the change.

## PARAMETERS

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

### -Restart
Indicates that this operation automatically restarts the computer to apply the change.

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

### None

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Disable-WmsVirtualDesktopRole](./Disable-WmsVirtualDesktopRole.md)

