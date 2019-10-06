---
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Windows.Appx.PackageManager.Commands.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
Module Name: Appx
ms.assetid: 0F0872D1-F99C-482A-96F2-CAF15622EEB1
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
title: Remove-AppxVolume
---

# Remove-AppxVolume

## SYNOPSIS
Removes an appx volume.

## SYNTAX

```
Remove-AppxVolume [-Volume] <AppxVolume[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-AppxVolume** cmdlet removes an **AppxVolume**.
You can only remove a volume after there are no apps staged to it for any user.
After you remove a volume, apps can no longer be added to it.

## EXAMPLES

### Example 1: Remove a volume by using an ID
```
PS C:\> Remove-AppxVolume -Volume {984786d3-0cae-49de-a68f-8bedb0ca260b}
```

This command removes a volume that has the specified media ID.

### Example 2: Remove a volume by using a path
```
PS C:\> Remove-AppxVolume -Volume E:\
```

This command removes a volume at the path E:\.

## PARAMETERS

### -Volume
Specifies the **AppxVolume** object to remove.

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

[Mount-AppxVolume](./Mount-AppxVolume.md)

