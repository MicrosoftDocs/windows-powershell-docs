---
description: Restores the Windows app to its initial configuration.
external help file: Microsoft.Windows.Appx.PackageManager.Commands.dll-help.xml
Module Name: Appx
ms.date: 05/15/2023
online version: https://learn.microsoft.com/powershell/module/appx/reset-appxpackage?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Reset-AppxPackage
---

# Reset-AppxPackage

## SYNOPSIS

Restores the Windows app to its initial configuration.

## SYNTAX

```
Reset-AppxPackage
 [-Package] <string>
 [-WhatIf]
 [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION

The `Reset-AppxPackage` cmdlet resets the app to its original settings, and the app will react
as a freshly installed app.

After resetting the app, any initial prompts by the app will be prompted for user input.

## EXAMPLES

### Example 1: Reset app package

```powershell
Reset-AppxPackage -Package publisher.package1_1.0.0.0_neutral__8wekyb3d8bbwe
```

This cmdlet resets the `publisher.package1_1.0.0.0_neutral__8wekyb3d8bbwe` application back to
its original settings.

## PARAMETERS

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

### -Package

Specifies the package full name (PFuN) of the app to reset.

```yaml
Type: System.String
Parameter Sets: None
Aliases: None

Required: True
Position: 0
Default value: None
Accept pipeline input: True
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

### System.String[]

### System.IO.FileInfo

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Package Manager API](http://go.microsoft.com/fwlink/?LinkId=245447)

[How to Add and Remove Apps](http://go.microsoft.com/fwlink/?LinkID=231020)

[Get-AppxPackage](./Get-AppxPackage.md)

[Get-AppxPackageManifest](./Get-AppxPackageManifest.md)

[Move-AppxPackage](./Move-AppxPackage.md)

[Remove-AppxPackage](./Remove-AppxPackage.md)
