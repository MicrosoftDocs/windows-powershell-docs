---
description: Use this topic to help manage MDOP technologies with Windows PowerShell.
external help file: AppVServerCmdlets.dll-Help.xml
ms.date: 12/05/2016
ms.devlang: powershell
schema: 2.0.0
title: Get-AppvServerPackageDeploymentConfiguration
---

# Get-AppvServerPackageDeploymentConfiguration

## SYNOPSIS
Returns a set of App-V server dynamic deployment configurations for the packages specified.

## SYNTAX

### ByName (Default)
```
Get-AppvServerPackageDeploymentConfiguration [-Name] <String> [[-Version] <String>] [<CommonParameters>]
```

### ByObject
```
Get-AppvServerPackageDeploymentConfiguration [-AppvServerPackage] <PackageVersion> [<CommonParameters>]
```

### By GUID
```
Get-AppvServerPackageDeploymentConfiguration [-PackageID] <Guid> [[-VersionID] <Guid>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AppvServerPackageDeploymentConfiguration** cmdlet returns a set of Microsoft Application Virtualization (App-V) server dynamic deployment configurations for the packages specified.

## EXAMPLES

### 1:
```

```

## PARAMETERS

### -AppvServerPackage
Specifies an array of **AppVServerPackage** objects.

```yaml
Type: PackageVersion
Parameter Sets: ByObject
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Specifies the friendly name of the package applied when the package was created.
This value is obtained using the package manifest.

```yaml
Type: String
Parameter Sets: ByName
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -PackageID
Specifies the GUID that uniquely identifies the package.
It can be found in the package manifest or by opening the package on the computer running the sequencer.
The package GUID is shared by all versions of a package.

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
If you do not specify a version, the cmdlet acts on all versions saved on computer.

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
If you do not specify a GUID, the cmdlet operates on all versions of the package.

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

### AppvServer.AppvServerPackage

## OUTPUTS

### String, system.string[]

## NOTES

## RELATED LINKS

