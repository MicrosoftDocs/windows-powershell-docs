---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.AppV.AppVClientPowerShell.dll-Help.xml
Module Name: AppvClient
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/appvclient/remove-appvclientpackage?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-AppvClientPackage
---

# Remove-AppvClientPackage

## SYNOPSIS
Removes the package from a computer.

## SYNTAX

### ByGuid (Default)
```
Remove-AppvClientPackage [-PackageId] <Guid> [-VersionId] <Guid> [<CommonParameters>]
```

### ByPackage
```
Remove-AppvClientPackage [-Package] <AppvClientPackage> [<CommonParameters>]
```

### ByName
```
Remove-AppvClientPackage [-Name] <String> [[-Version] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-AppvClientPackage** cmdlet removes the package from computer that runs the Microsoft Application Virtualization (App-V) client.
The cmdlet deletes the **AppvClientPackage** object.

## EXAMPLES

### Example 1: Remove a version of a package by using the pipeline operator
```
PS C:\> Get-AppvPackage -Name "MyPackage" -Version 1 | Remove-Package
```

This command gets version 1 of the package named MyPackage, and then removes it from the computer.

### Example 2: Remove a version of a package
```
PS C:\> Remove-Package -Name "MyPackage" -Version 1
```

This command removes version 1 of the package named MyPackage from the computer.

## PARAMETERS

### -Name
Specifies the friendly name of the package given during sequencing.
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
Specifies the package ID that uniquely identifies the package.
It can be found in the package manifest or by opening the package in the sequencer.
The package ID is shared by all versions of a specific package.

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
Specifies a GUID that differentiates a package version from other versions, whether older, newer, or of a different lineage.
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

## NOTES

## RELATED LINKS

[Add-AppvClientPackage](./Add-AppvClientPackage.md)

[Get-AppvClientPackage](./Get-AppvClientPackage.md)

[Mount-AppvClientPackage](./Mount-AppvClientPackage.md)

[Publish-AppvClientPackage](./Publish-AppvClientPackage.md)

[Repair-AppvClientPackage](./Repair-AppvClientPackage.md)

[Set-AppvClientPackage](./Set-AppvClientPackage.md)

[Stop-AppvClientPackage](./Stop-AppvClientPackage.md)

[Unpublish-AppvClientPackage](./Unpublish-AppvClientPackage.md)

