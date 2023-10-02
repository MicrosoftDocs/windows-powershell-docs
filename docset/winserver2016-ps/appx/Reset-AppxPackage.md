---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Windows.Appx.PackageManager.Commands.dll-help.xml
Module Name: Appx
ms.date: 10/20/2020
online version: https://learn.microsoft.com/powershell/module/appx/reset-appxpackage?view=windowsserver2016-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Reset-AppxPackage
---

# Reset-AppxPackage

## SYNOPSIS

Starting at Windows 10 Insider Preview Build 20215 you get access to the `Reset-AppxPackage` PowerShell Cmdlet for use in resetting your installed Windows Apps.

Restores the Windows app to its initial configuration.

## SYNTAX

```PowerShell
Reset-AppxPackage
[-Package] <string>
[-WhatIf] 
[-Confirm] 
[<CommonParameters>]
```

## DESCRIPTION
The **Reset-AppxPackage** cmdlet will reset the app to its original settings, and the app will react as a freshly installed app. 

After resetting the app, any initial prompts by the app will be prompted for user input. 

## EXAMPLES

### Example 1: Reset app package
```
PS C:\> Reset-AppxPackage -Package publisher.package1_1.0.0.0_neutral__8wekyb3d8bbwe
```

This cmdlet will reset the `publisher.package1_1.0.0.0_neutral__8wekyb3d8bbwe` application back to its original settings.

## PARAMETERS

### -Package
Specifies the package full name (PFuN) of the app which will be reset.

```yaml
Type: String[]
Parameter Sets: None
Aliases: None

Required: True
Position: 0
Default value: None
Accept pipeline input: True
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

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
