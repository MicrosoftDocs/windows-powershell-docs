---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.AppV.AppVClientPowerShell.dll-Help.xml
Module Name: AppvClient
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/appvclient/unpublish-appvclientpackage?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Unpublish-AppvClientPackage
---

# Unpublish-AppvClientPackage

## SYNOPSIS
Removes the extension points for packages.

## SYNTAX

### ByGuid (Default)
```
Unpublish-AppvClientPackage [-Global] [-UserSID <String>] [-PackageId] <Guid> [-VersionId] <Guid>
 [<CommonParameters>]
```

### ByPackage
```
Unpublish-AppvClientPackage [-Global] [-UserSID <String>] [-Package] <AppvClientPackage> [<CommonParameters>]
```

### ByName
```
Unpublish-AppvClientPackage [-Global] [-UserSID <String>] [-Name] <String> [[-Version] <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Unpublish-AppvClientPackage** cmdlet removes all the extension points of the specified packages.
The package contents remain on the target computer.
The package is still added on the client and the appropriate **AppvClientPackage** object persists.

The package can be unpublished for the current user or if all users that log on to the target computer.

## EXAMPLES

### Example 1: Unpublish a version of a package
```
PS C:\> Unpublish-AppvClientPackage -Name "MyApp" -Version 3
```

This command unpublishes version 3 of the package named MyApp.

### Example 2: Unpublish a version of a package for all users
```
PS C:\> Unpublish-AppvClientPackage -Name "MyApp" -Version 3 -Global
```

This command unpublishes version 3 of the package named MyApp for all users on the computer.

## PARAMETERS

### -Global
Indicates that the packages are unpublished to all users that log into the targeted computer.
Otherwise, the packages are only unpublished to the currently running user.

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
The package ID is shared by all versions of a package.

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

### -UserSID
Specifies the SID of the intended user, in the form of S-1-2-34-56789012-3456789012-345678901-2345.
This cmdlet parameter requires elevated rights to run.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Version
Specifies the version of an App-V package in one specific lineage.
If you do not specify this parameter, the cmdlet operates on the latest version found.

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
Specifies a GUID that differentiates a package version from other versions, whether older, newer, or of a different lineage.
If you do not specify this parameter, the cmdlet operates on the latest version of the package.

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

[Repair-AppvClientPackage](./Repair-AppvClientPackage.md)

[Set-AppvClientPackage](./Set-AppvClientPackage.md)

[Stop-AppvClientPackage](./Stop-AppvClientPackage.md)

