---
description: Use this topic to help manage MDOP technologies with Windows PowerShell.
external help file: Microsoft.AppV.AppVClientPowerShell.dll-Help.xml
ms.date: 12/05/2016
ms.devlang: powershell
schema: 2.0.0
title: Get-AppvClientPackage
---

# Get-AppvClientPackage

## SYNOPSIS
Returns App-V Client Packages.

## SYNTAX

### ByName (Default)
```
Get-AppvClientPackage [[-Name] <String>] [[-Version] <String>] [-All] [<CommonParameters>]
```

### ByGuid
```
Get-AppvClientPackage [-PackageId] <Guid> [[-VersionId] <Guid>] [-All] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AppvClientPackage** cmdlet returns a set of Microsoft Application Virtualization (App-V) Client Packages based on the criteria provided.

## EXAMPLES

### Example 1: Get packages that have names that match a string
```
PS C:\> Get-AppvClientPackage -Name "MyApp*" -All
```

This command gets the set of packages that have names beginning with the string MyApp.

### Example 2: Get a specific version of a package by name
```
PS C:\> Get-AppvClientPackage -Name "MyApp" -Version 4
```

This command gets the version 4 of the package named MyApp.

### Example 3: Get a package by using its package ID
```
PS C:\> Get-AppvClientPackage -PackageID 793afd37-bd68-4ea1-859a-669f6afd0aa8
```

This command gets the package with the package ID of 793afd37-bd68-4ea1-859a-669f6afd0aa8.

## PARAMETERS

### -All
Indicates that the cmdlet uses the set of all packages added to the computers as the searchable set.
If not provided, the cmdlet only uses packages that are entitled to the current user.

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

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PackageId
Specifies the GUID that uniquely identifies the package.
It can be found in the package manifest or by opening the package in the App-V Sequencer.
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

### -Version
Specifies the version of an App-V package in one specific lineage.
If you do not specify this parameter, the cmdlet operates on available versions of the package on the target computer.

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
Specifies the GUID that differentiates a package version from other versions, whether older, newer, or of a completely different lineage.
If you do specify this parameter, the cmdlet operateson all versions of a package.

```yaml
Type: Guid
Parameter Sets: ByGuid
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.AppV.AppvClientPowerShell.AppvClientPackage

## NOTES
* If you do not specify any parameters, the cmdlet returns a set of all packages on the computer.
* The cmdlet checks that you have permissions to perform the specific action. If not, the cmdlet returns the following error: The action could not be performed due to current App-V permissions. Please modify the permissions and try the operation again.
* If the cmdlet cannot find the package, the cmdlet returns the following error: The specified package(s) could not be found. An error code is returned.

## RELATED LINKS

[Add-AppvClientPackage](./add-appvclientpackage.md)

[Mount-AppvClientPackage](./mount-appvclientpackage.md)

[Publish-AppvClientPackage](./publish-appvclientpackage.md)

[Publish-AppvClientPackage](./publish-appvclientpackage.md)

[Remove-AppvClientPackage](./remove-appvclientpackage.md)

[Repair-AppvClientPackage](./repair-appvclientpackage.md)

[Set-AppvClientPackage](./set-appvclientpackage.md)

[Stop-AppvClientPackage](./stop-appvclientpackage.md)

[Unpublish-AppvClientPackage](./unpublish-appvclientpackage.md)
