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
ms.assetid: 1A198BA9-0F18-4B04-9048-86DD4F73234E
ms.date: 12/05/2016
ms.devlang: powershell
ms.topic: reference
online version: 
schema: 2.0.0
title: Unpublish-AppvServerPackage
---

# Unpublish-AppvServerPackage

## SYNOPSIS
Unpublishes packages.

## SYNTAX

### ByName (Default)
```
Unpublish-AppvServerPackage [[-Name] <String>] [[-Version] <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByObject
```
Unpublish-AppvServerPackage [-AppvServerPackage] <PackageVersion[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### By GUID
```
Unpublish-AppvServerPackage [-PackageID] <Guid> [[-VersionID] <Guid>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Unpublish-AppvServerPackage** cmdlet unpublishes a package.
All connected publishing servers no longer push the specified packages to entitled users.

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
Specifies the GUID that uniquely identifies the package.
It can be found in the package manifest or by opening the package in the Microsoft Application Virtualization (App-V) sequencer.
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
Specifies the version of an App-V package in a lineage.
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
Specifies a GUID that differentiates a package version from other versions, whether older, newer, or of a completely different lineage.
If you do not specify this parameter, the cmdlet operates on all versions of the package.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### AppvServer.AppvServerPackage

## OUTPUTS

## NOTES
* If the packages do not exist, the unpublish operation fails for those packages. The cmdlet returns the following error: The following packages could not be found on the system \<list of packages\>.
* If you do not specify version information, the cmdlet unpublishes all versions of the package.
* If you do not specify any parameters, the cmdlet unpublishes all packages on the computer. The cmdlet returns a warning before it runs this operation.

## RELATED LINKS

[Get-AppvServerPackage](./Get-AppvServerPackage.md)

[Grant-AppvServerPackage](./Grant-AppvServerPackage.md)

[Import-AppvServerPackage](./Import-AppvServerPackage.md)

[Publish-AppvServerPackage](./Publish-AppvServerPackage.md)

[Remove-AppvServerPackage](./Remove-AppvServerPackage.md)

[Set-AppvServerPackage](./Set-AppvServerPackage.md)


