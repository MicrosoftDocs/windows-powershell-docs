---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Windows.Appx.PackageManager.Commands.dll-Help.xml
Module Name: Appx
ms.date: 05/15/2023
online version: https://learn.microsoft.com/powershell/module/appx/move-appxpackage?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Move-AppxPackage
---

# Move-AppxPackage

## SYNOPSIS
Moves a package from its current location to another appx volume.

## SYNTAX

```
Move-AppxPackage [-Package] <String[]> [-Volume] <AppxVolume> [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

The `Move-AppxPackage` cmdlet moves a package from its current location to another **AppxVolume**.
The new location must be a volume that Package Manager knows about and that's mounted. This cmdlet
also moves your application data to the specified volume.

## EXAMPLES

### Example 1: Move a package to a volume specified by a path

```powershell
Move-AppxPackage -Package "package1_1.0.0.0_neutral__8wekyb3d8bbwe" -Volume F:\
```

This command moves package that has the specified name to volume `F:\`. This cmdlet also moves your
app data.

### Example 2: Move a package to a volume specified by an ID

```powershell
$params = @{
    Package = 'package1_1.0.0.0_neutral__8wekyb3d8bbwe'
    Volume  = '{d2a4d1f4-f45a-46f3-a419-160ab52af091}'
}
Move-AppxPackage @params
```

This command moves package that has the specified name to the volume that has the specified media
ID. This cmdlet also moves your app data.

## PARAMETERS

### -Package

Specifies an **AppxPackage** object or the full name of a package. This cmdlet moves the package
that this parameter specifies.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Volume

Specifies an **AppxVolume** object. The cmdlet moves the package to the volume that this parameter
specifies.

```yaml
Type: AppxVolume
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
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

[Add-AppxPackage](./Add-AppxPackage.md)

[Get-AppxPackage](./Get-AppxPackage.md)

[Remove-AppxPackage](./Remove-AppxPackage.md)
