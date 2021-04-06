---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-kaunu
author: Kateyanne
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MultiPointVdi.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: 
ms.topic: reference
online version: 
schema: 2.0.0
title: Disable-WmsVirtualDesktopRole
ms.reviewer:
ms.assetid: 11A337BF-F411-4502-AF18-B2AC32880838
---

# Disable-WmsVirtualDesktopRole

## SYNOPSIS
Disables a Hyper-V virtual desktop role.

## SYNTAX

```
Disable-WmsVirtualDesktopRole [-Restart] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Disable-WmsVirtualDesktopRole** cmdlet switches all stations from Virtual Desktop Infrastructure (VDI) mode to Remote Desktop Session Host (RDSH) mode, and then uninstalls the Hyper-V virtual desktop role.
The system reboots to apply the changes if you specify the *Restart* parameter.

## EXAMPLES

### Example 1: Disable a virtual desktop
```
PS C:\> Disable-WmsVirtualDesktopRole -Restart
```

This command switches all stations from Remote Desktop Virtualization Host (RDVH) sessions to RDSH sessions, removes the Hyper-V virtual desktop role, and automatically restarts the computer to apply the changes.

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

[Enable-WmsVirtualDesktopRole](./Enable-WmsVirtualDesktopRole.md)

