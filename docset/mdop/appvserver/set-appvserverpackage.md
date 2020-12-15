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
ms.assetid: A6182D54-5762-441B-B63F-0A6A54FD2ED1
ms.date: 12/05/2016
ms.devlang: powershell
ms.topic: reference
online version: 
schema: 2.0.0
title: Set-AppvServerPackage
---

# Set-AppvServerPackage

## SYNOPSIS
Applies a dynamic deployment or user configuration file to a package.

## SYNTAX

### ByObject
```
Set-AppvServerPackage [-AppvServerPackage] <PackageVersion> [[-Groups] <String[]>]
 [[-DynamicDeploymentConfigurationPath] <String>] [[-DynamicUserConfigurationPath] <String>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### ByName
```
Set-AppvServerPackage [[-Groups] <String[]>] [-Name] <String> [[-Version] <String>]
 [[-DynamicDeploymentConfigurationPath] <String>] [[-DynamicUserConfigurationPath] <String>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### By GUID
```
Set-AppvServerPackage [[-Groups] <String[]>] [-PackageID] <Guid> [[-VersionID] <Guid>]
 [[-DynamicDeploymentConfigurationPath] <String>] [[-DynamicUserConfigurationPath] <String>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-AppvServerPackage** cmdlet applies a dynamic deployment or user configuration file to a package.

Only one deployment configuration can be entitled to a package.

Multiple user configuration files can be applied to a package to specific Active Directory group entitlements.

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

### -DynamicDeploymentConfigurationPath
Specifies the path to a dynamic deployment configuration file for the specified Microsoft Application Virtualization (App-V) package.
The cmdlet uses the dynamic deployment configuration file to override the default behavior provided in the package's manifest.

If you do not specify this parameter, the App-V agent assign the Default Machine Policy to the App-V package to be added.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DynamicUserConfigurationPath
Specifies the path to a dynamic user configuration file for the specified App-V package.
The cmdlet uses the user policy file to override the default behavior provided in the package manifest.
If you do not specify this parameter, the default user policy will be applied to the package.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Groups
Specifies an array of names of Active Directory groups.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
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
Specifies the GUID that uniquely identifies the package.
It can be found in the package manifest or by opening the package in the App-V sequencer.
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
Specifies the version of an App-V package in one specific lineage.
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
* If the cmdlet cannot find a package cannot be found, the cmdlet returns the following error: The specified package could not be found on the system. The cmdlet fails the operation.
* If you specify an invalid group, the cmdlet returns the following error: The provided entitlements are not valid. The cmdlet fails the operation.
* If you do not specify version information, the cmdlet acts on all available versions of the package.
* Do not specify Active Directory entitlements when supplying a deployment configuration. If so, the cmdlet returns an error.
* Do not set both deployment configuration and user configuration at the same time.

## RELATED LINKS

[Get-AppvServerPackage](./Get-AppvServerPackage.md)

[Grant-AppvServerPackage](./Grant-AppvServerPackage.md)

[Import-AppvServerPackage](./Import-AppvServerPackage.md)

[Publish-AppvServerPackage](./Publish-AppvServerPackage.md)

[Remove-AppvServerPackage](./Remove-AppvServerPackage.md)

[Unpublish-AppvServerPackage](./Unpublish-AppvServerPackage.md)


