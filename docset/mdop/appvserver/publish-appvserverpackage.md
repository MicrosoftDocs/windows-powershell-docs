---
ms.technology: powershell-mdop
ms.mktglfcycl: manage
ms.author: kenwith
ms.prod: w10
ms.sitesec: library
author: kenwith
description: Use this topic to help manage MDOP technologies with Windows PowerShell.
external help file: AppVServerCmdlets.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro 
ms.assetid: 5A42C293-8C23-4531-B08A-3ECCCA63E83E
ms.date: 2016-12-05
ms.devlang: powershell
ms.topic: reference
online version: 
schema: 2.0.0
title: Publish-AppvServerPackage
---

# Publish-AppvServerPackage

## SYNOPSIS
Publish a package.

## SYNTAX

### ByName (Default)
```
Publish-AppvServerPackage [[-Name] <String>] [[-Version] <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByObject
```
Publish-AppvServerPackage [-AppvServerPackage] <PackageVersion[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### By GUID
```
Publish-AppvServerPackage [-PackageID] <Guid> [[-VersionID] <Guid>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Publish-AppvServerPackage** cmdlet publishes a package.
All connected publishing servers push the specified packages to entitled users.

## EXAMPLES

### 1:
```

```

## PARAMETERS

### -AppvServerPackage
Specifies an array of **AppVServerPackage** objects.

```yaml
Type: PackageVersion[]
Parameter Sets: ByObject
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

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
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -PackageID
Specifies the package GUID that uniquely identifies the package.
The GUID can be found in the package manifest or by opening the package in the Microsoft Application Virtualization (App-V) sequencer.
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
Specifies the version of an App-V package in one lineage.
If no version is supplied, the cmdlet acts on all versions saved to computer.

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
Specifies a version ID that differentiates a package version from other versions, whether older, newer, or of a completely different lineage.
If this parameter is not specified, the cmdlet operates on all versions of the package.

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

### -Confirm
Prompts you for confirmation before running the cmdlet.Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### AppvServer.AppvServerPackage

## OUTPUTS

## NOTES
* If the specified packages do not exist, the publish operation fails for those packages. The cmdlet returns the following error: The following packages could not be found on the system \<list of packages\>.
* If you do not specify a version, the cmdlet publishes all versions of the package.
* If you do not specify any parameters, the cmdlet publishes all packages on the computer. The cmdlet returns a warning before it runs this operation.

## RELATED LINKS

[Get-AppvServerPackage](./Get-AppvServerPackage.md)

[Grant-AppvServerPackage](./Grant-AppvServerPackage.md)

[Import-AppvServerPackage](./Import-AppvServerPackage.md)

[Remove-AppvServerPackage](./Remove-AppvServerPackage.md)

[Set-AppvServerPackage](./Set-AppvServerPackage.md)

[Unpublish-AppvServerPackage](./Unpublish-AppvServerPackage.md)


