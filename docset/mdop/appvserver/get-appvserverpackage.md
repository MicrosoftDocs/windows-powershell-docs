---
ms.technology: 
ms.mktglfcycl: manage
ms.author: v-kaunu
ms.prod: w10
ms.sitesec: library
author: Kateyanne
description: Use this topic to help manage MDOP technologies with Windows PowerShell.
external help file: AppVServerCmdlets.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro 
ms.assetid: 49957EAE-B6B4-443B-9504-BF536F5A7162
ms.date: 12/05/2016
ms.devlang: powershell
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-AppvServerPackage
---

# Get-AppvServerPackage

## SYNOPSIS
Returns App-V Server packages.

## SYNTAX

### ByName (Default)
```
Get-AppvServerPackage [[-Name] <String>] [[-Version] <String>] [<CommonParameters>]
```

### By GUID
```
Get-AppvServerPackage [-PackageID] <Guid> [[-VersionID] <Guid>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AppvServerPackage** cmdlet returns a set of Microsoft Application Virtualization (App-V) Server packages based on the criteria provided.

## EXAMPLES

### Example 1: Return packages that include a partial name
```
PS C:\> Get-AppvServerPackage -Name "Office*"
```

This command returns all packages that have a name that matches the criteria specified in the *Name* parameter.

### Example 2: Return a single version of a package
```
PS C:\> Get-AppvServerPackage -Name "Office" -Version "2"
```

This command returns the single package that has the specified name and version.

### Example 3: Return all versions of a package
```
PS C:\> Get-AppvServerPackage -PackageID A12D32445F
```

This command returns all versions of the package that have the specified package GUID.

### Example 4: Return all the packages
```
PS C:\> Get-AppvServerPackage
```

This command returns a list of all the packages on the system.

## PARAMETERS

### -Name
Specifies the friendly name of the package given when the package was created.
This value is obtained from the package manifest.

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

### -PackageID
Specifies the package GUID that uniquely identifies the package.
It can be found in the package manifest or by opening the package using the sequencer.
The Package GUID is shared by all versions of a package.

```yaml
Type: Guid
Parameter Sets: By GUID
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Version
Specifies the version of an App-V package.
If you do not specify a version, the cmdlet acts on all versions saved on the computer.

```yaml
Type: String
Parameter Sets: ByName
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -VersionID
Specifies a GUID that differentiates a package version from other versions.
If you do not specify a version GUID, the cmdlet operates on all versions of the package.

```yaml
Type: Guid
Parameter Sets: By GUID
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### AppvServer.AppvServerPackage

## NOTES

## RELATED LINKS

[Grant-AppvServerPackage](./Grant-AppvServerPackage.md)

[Import-AppvServerPackage](./Import-AppvServerPackage.md)

[Publish-AppvServerPackage](./Publish-AppvServerPackage.md)

[Remove-AppvServerPackage](./Remove-AppvServerPackage.md)

[Set-AppvServerPackage](./Set-AppvServerPackage.md)

[Unpublish-AppvServerPackage](./Unpublish-AppvServerPackage.md)


