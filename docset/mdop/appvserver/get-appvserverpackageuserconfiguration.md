---
description: Use this topic to help manage MDOP technologies with Windows PowerShell.
external help file: AppVServerCmdlets.dll-Help.xml
ms.date: 12/05/2016
ms.devlang: powershell
schema: 2.0.0
title: Get-AppvServerPackageUserConfiguration
---

# Get-AppvServerPackageUserConfiguration

## SYNOPSIS
Returns App-V Server Dynamic user configurations applied to a user group for a set of packages.

## SYNTAX

### ByName (Default)
```
Get-AppvServerPackageUserConfiguration -Group <String> [-Name] <String> [<CommonParameters>]
```

### ByObject
```
Get-AppvServerPackageUserConfiguration [-AppvServerPackage] <PackageVersion> -Group <String>
 [<CommonParameters>]
```

### By GUID
```
Get-AppvServerPackageUserConfiguration -Group <String> [-PackageID] <Guid> [[-VersionID] <Guid>]
 [<CommonParameters>]
```

### By Name
```
Get-AppvServerPackageUserConfiguration -Group <String> [[-Version] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AppvServerPackageUserConfiguration** cmdlet returns a set of Microsoft Application Virtualization (App-V) Server Dynamic user configurations (Strings) applied to a given user group for specified packages.

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

### -Group
Specifies the name of the Active Directory group.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the friendly name of the package given when the package was created.
This value is obtained from the package manifest.

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
Specifies a GUID that uniquely identifies the package.
This GUID can be found in the package manifest or by opening the package in the App-V sequencer.
The package GUID is shared by all versions of a specific package.

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
Specifies the version of an App-V package in one lineage.
If no version is supplied, the operation acts on all versions saved to computer.

```yaml
Type: String
Parameter Sets: By Name
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -VersionID
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

### System.String[]

## NOTES

## RELATED LINKS

