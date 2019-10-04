---
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Windows.Appx.PackageManager.Commands.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
Module Name: Appx
ms.assetid: 2EEB3888-4834-4458-8E02-156191B6AF0B
ms.author: v-anbarr
ms.date: 12/20/2016
ms.mktglfcycl: manage
ms.prod: w10
ms.reviewer:
ms.sitesec: library
ms.technology: powershell-windows
ms.topic: reference
online version:
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
The **Add-AppxVolume** cmdlet adds an **AppxVolume** for the Package Manager to advertise.
After you add a volume, appx deployment operations can use that volume as a target.
This cmdlet returns the volume that it adds.
Note, the *Path* parameter must be specified as a drive letter followed by "WindowsApps" as the directory.
Not using the aforementioned format could lead to inconsistent behavior in the application model subsystems or the volume itself; for more information see the examples section.

## EXAMPLES

### Example 1: Add a volume
```
PS C:\> Add-AppxVolume -Path "E:\WindowsApps"
```

This command adds the volume E:\WindowsApps to Package Manager.

## PARAMETERS

### -Path
Specifies the path of the mount point of the volume that this cmdlet adds.

```yaml
Type: String[]
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

### Microsoft.Appx.PackageManager.Commands.AppxVolume
This cmdlet returns the **AppxVolume** object that it adds.

## NOTES

## RELATED LINKS

[Dismount-AppxVolume](./Dismount-AppxVolume.md)

[Get-AppxVolume](./Get-AppxVolume.md)

[Mount-AppxVolume](./Mount-AppxVolume.md)

[Remove-AppxVolume](./Remove-AppxVolume.md)

