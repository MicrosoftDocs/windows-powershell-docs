---
author: Kateyanne
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Windows.Appx.PackageManager.Commands.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
Module Name: Appx
ms.assetid: 0B2E924A-1D72-4E37-B700-FF0A6EF8BC67
ms.author: v-kaunu
ms.date: 12/20/2016
ms.mktglfcycl: manage
ms.prod: w10
ms.reviewer:
ms.sitesec: library
ms.technology: 
ms.topic: reference
online version:
schema: 2.0.0
title: Mount-AppxVolume
---

# Mount-AppxVolume

## SYNOPSIS
Mounts an appx volume.

## SYNTAX

```
Mount-AppxVolume [-Volume] <AppxVolume[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Mount-AppxVolume** cmdlet mounts an **AppxVolume**.
After you mount a volume, all apps that are deployed to that target become accessible.

## EXAMPLES

### Example 1: Mount a volume by using a path
```
PS C:\> Mount-AppxVolume -Volume E:\
```

This command mounts a volume at the path E:\.

### Example 2: Mount a volume by using an ID
```
PS C:\> Mount-AppxVolume -Volume {7e62a691-398e-4fbe-819a-64f1e407777a}
```

This command mounts a volume that has the specified media ID.

## PARAMETERS

### -Volume
Specifies the **AppxVolume** object to mount.

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

[Add-AppxVolume](./Add-AppxVolume.md)

[Dismount-AppxVolume](./Dismount-AppxVolume.md)

[Get-AppxVolume](./Get-AppxVolume.md)

[Remove-AppxVolume](./Remove-AppxVolume.md)

