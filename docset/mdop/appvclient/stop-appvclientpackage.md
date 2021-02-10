---
ms.technology: 
ms.mktglfcycl: manage
ms.author: v-kaunu
ms.prod: w10
ms.sitesec: library
author: Kateyanne
description: Use this topic to help manage MDOP technologies with Windows PowerShell.
external help file: Microsoft.AppV.AppVClientPowerShell.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro 
ms.assetid: CBB6838A-9DE9-44EB-ADFE-7B3156FF5C5D
ms.date: 12/05/2016
ms.devlang: powershell
ms.topic: reference
online version: 
schema: 2.0.0
title: Stop-AppvClientPackage
---

# Stop-AppvClientPackage

## SYNOPSIS
Shuts down virtual environments for specified packages.

## SYNTAX

### ByGuid (Default)
```
Stop-AppvClientPackage [-Global] [-PackageId] <Guid> [-VersionId] <Guid> [<CommonParameters>]
```

### ByPackage
```
Stop-AppvClientPackage [-Global] [-Package] <AppvClientPackage> [<CommonParameters>]
```

### ByName
```
Stop-AppvClientPackage [-Global] [-Name] <String> [[-Version] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Stop-AppvClientPackage** cmdlet shuts down the virtual environment for the specified packages.
All applications and processes within that package are forced to shut down.
Any unsaved application data is lost.

## EXAMPLES

### Example 1: Shut down a virtual environment for a version of a package
```
PS C:\> Stop-AppvClientPackage -Name "MyPackage" -Version 2
```

This command shuts down the virtual environment of version 2 of package named MyPackage.

### Example 2: Shut down a virtual environment for all versions of a package
```
PS C:\> Get-AppvClientPackage -Name "MyPackage" | Stop-AppvClientPackage
```

This command gets all versions of the package named MyPackage, and then shuts down the virtual environment for those results.

## PARAMETERS

### -Global
Specifies that the cmdlet shuts down virtual environments for the specified packages for all users on the computer.
Usage of *Global* parameter requires administrative privileges.

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
Not Specified

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

### -Version
Specifies the version of an App-V package in a lineage.
If you do not specify this parameter, the cmdlet operateson all available versions of the package on the computer.

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
Specifies a GUID that differentiates a package version from other versions, whether older, newer, or of a completely different lineage.
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

[Publish-AppvClientPackage](./Publish-AppvClientPackage.md)

[Remove-AppvClientPackage](./Remove-AppvClientPackage.md)

[Repair-AppvClientPackage](./Repair-AppvClientPackage.md)

[Set-AppvClientPackage](./Set-AppvClientPackage.md)

[Unpublish-AppvClientPackage](./Unpublish-AppvClientPackage.md)


