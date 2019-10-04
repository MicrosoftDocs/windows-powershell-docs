---
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Windows.Appx.PackageManager.Commands.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
Module Name: Appx
ms.assetid: 4D2BE4AE-EBBD-4225-8EF1-ECA25C58411E
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
title: Get-AppxVolume
---

# Get-AppxVolume

## SYNOPSIS
Gets appx volumes for the computer.

## SYNTAX

### DefaultParameterSet
```
Get-AppxVolume [[-Path] <String>] [<CommonParameters>]
```

### OnlineParameterSet
```
Get-AppxVolume [[-Path] <String>] [-Online] [<CommonParameters>]
```

### OfflineParameterSet
```
Get-AppxVolume [[-Path] <String>] [-Offline] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AppxVolume** cmdlet gets a list of **AppxVolume** objects known to the computer.
Volumes can be added by the user or a device, for instance, by using Storage Sense.

## EXAMPLES

### Example 1: Get all the volumes
```
PS C:\> Get-AppxVolume
```

The command gets all the **AppxVolume** objects on the computer.

### Example 2: Get the volume at a path
```
PS C:\> Get-AppxVolume -Path F:\
```

This command gets the **AppxVolume** at the path F:\.

### Example 3: Get mounted volumes
```
PS C:\> Get-AppxVolume -Online
```

This command gets only **AppxVolume** objects that are currently mounted on the computer.

### Example 4: Get volumes that are note mounted
```
PS C:\> Get-AppxVolume -Offline
```

This command gets the **AppxVolume** objects that not currently mounted on the computer.

## PARAMETERS

### -Offline
Indicates that this cmdlet returns only volumes that are currently dismounted.

```yaml
Type: SwitchParameter
Parameter Sets: OfflineParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Online
Indicates that this cmdlet returns only volumes that are currently mounted.

```yaml
Type: SwitchParameter
Parameter Sets: OnlineParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path
Specifies the path of the mount point of a volume.
This cmdlet gets a volume at the location that this parameter specifies.

```yaml
Type: String
Parameter Sets: DefaultParameterSet
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: OnlineParameterSet, OfflineParameterSet
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Appx.PackageManager.Commands.AppxVolume

## NOTES

## RELATED LINKS

[Add-AppxVolume](./Add-AppxVolume.md)

[Dismount-AppxVolume](./Dismount-AppxVolume.md)

[Mount-AppxVolume](./Mount-AppxVolume.md)

[Remove-AppxVolume](./Remove-AppxVolume.md)

