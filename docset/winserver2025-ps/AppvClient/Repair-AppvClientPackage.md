---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.AppV.AppVClientPowerShell.dll-Help.xml
Module Name: AppvClient
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/appvclient/repair-appvclientpackage?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Repair-AppvClientPackage
---

# Repair-AppvClientPackage

## SYNOPSIS
Resets the user settings of a package.

## SYNTAX

### ByGuid (Default)
```
Repair-AppvClientPackage [-Global] [-UserState] [-Extensions] [-PackageId] <Guid> [-VersionId] <Guid>
 [<CommonParameters>]
```

### ByPackage
```
Repair-AppvClientPackage [-Global] [-UserState] [-Extensions] [-Package] <AppvClientPackage>
 [<CommonParameters>]
```

### ByName
```
Repair-AppvClientPackage [-Global] [-UserState] [-Extensions] [-Name] <String> [[-Version] <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Repair-AppvClientPackage** cmdlet deletes the user settings and reset the extension points of the package.
Resetting the settings causes permanent loss of any user-specific application settings in the package.
The settings are reset to their original state when the package was originally added to the system.

## EXAMPLES

### Example 1: Delete user state for a version of a package
```
PS C:\> Repair-AppvClientPackage -Name "MyApp" -Version 3
```

This command deletes the user state of version 3 of the package named MyApp.

### Example 2: Delete user state for packages that have a name that matches a string
```
PS C:\> Get-AppvClientPackage -Name "MyA*" | Repair-AppvClientPackage
```

This command gets all packages that have the string MyA in the name, and then delete the user state for those packages.

## PARAMETERS

### -Extensions
Indicates that this cmdlet repairs the extension points of a package only, and does not delete the user state of the package.

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

### -Global
Indicates that this cmdlet repairs the extension points for the provided packages for all users that log into the targeted computer.
Otherwise, the extension points of the packages are only repaired for the currently running user.

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

### -Name
Specifies the friendly name of the package given during Sequencing time.
This value is obtained from the package manifest.

```yaml
Type: String
Parameter Sets: ByName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Package
Specifies an App-V package.

```yaml
Type: AppvClientPackage
Parameter Sets: ByPackage
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -PackageId
Specifies a GUID that uniquely identifies the package.
It can be found in the package manifest or by opening the package in the Microsoft Application Virtualization (App-V) Sequencer.
The Package ID is shared by all versions of a package.

```yaml
Type: Guid
Parameter Sets: ByGuid
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UserState
Indicates that the cmdlet deletes the user state of the package only, and does not perform a repair on the extension points.

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

### -Version
Specifies the version of an App-V package in a lineage.
If you do not specify this parameter, the cmdlet operates on all versions on the computer.

```yaml
Type: String
Parameter Sets: ByName
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VersionId
Specifies the GUID that differentiates a package version from other versions, whether older, newer, or of a different lineage.
If you do not specify this parameter, the cmdlet operates on all versions of the package.

```yaml
Type: Guid
Parameter Sets: ByGuid
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.AppvAgent.AppvClientPackage

## OUTPUTS

### Microsoft.AppvAgent.AppvClientPackage

## NOTES

## RELATED LINKS

[Add-AppvClientPackage](./Add-AppvClientPackage.md)

[Get-AppvClientPackage](./Get-AppvClientPackage.md)

[Mount-AppvClientPackage](./Mount-AppvClientPackage.md)

[Publish-AppvClientPackage](./Publish-AppvClientPackage.md)

[Remove-AppvClientPackage](./Remove-AppvClientPackage.md)

[Set-AppvClientPackage](./Set-AppvClientPackage.md)

[Stop-AppvClientPackage](./Stop-AppvClientPackage.md)

[Unpublish-AppvClientPackage](./Unpublish-AppvClientPackage.md)

