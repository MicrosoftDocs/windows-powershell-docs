---
ms.technology: powershell-mdop
ms.mktglfcycl: manage
ms.author: v-anbarr
ms.prod: w10
ms.sitesec: library
author: andreabarr
description: Use this topic to help manage MDOP technologies with Windows PowerShell.
external help file: Microsoft.AppV.AppVClientPowerShell.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro 
ms.assetid: 80743DEC-763C-4D64-8043-8A6F10F23284
ms.date: 2016-12-05
ms.devlang: powershell
ms.topic: reference
online version: 
schema: 2.0.0
title: Add-AppvClientPackage
---

# Add-AppvClientPackage

## SYNOPSIS
Adds a package to a computer running the App-V client.

## SYNTAX

```
Add-AppvClientPackage [-Path] <String> [[-DynamicDeploymentConfiguration] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Add-AppvClientPackage** cmdlet adds a new package to a computer running the Microsoft Application Virtualization (App-V) client.
You can also upgrade an existing package running on a computer running the App-V client.
The newly added package or package version is registered with the App-V client.

If the package already exists on the computer, but the package to be added is a different version, the new version is added.
Existing versions will remain unchanged.

## EXAMPLES

### Example 1: Add a package to the client
```
PS C:\> Add-AppvClientPackage -Path "http://MyServer/content/package.APPV"
```

This command adds a new package to the client computer.
If the package is a different version of an already existing package, the App-V agent adds this new version, but does not modify any existing versions.
Since no computer policy is provided, the package receives the default computer policy.

### Example 2: Add a package with a configuration file
```
PS C:\> Add-AppvClientPackage -Path "http://MyServer/content/package.appv" -DynamicDeploymentConfiguration "C:\MyConfigfiles\DynamicDeploymentConfig.xml"
```

This command adds a package with a Dynamic Deployment Configuration file.

### Example 3: Add a package to the client and store the result
```
PS C:\> $Package = Add-AppvClientPackage -Path "http://MyServer/content/package.APPV"
```

This command adds a new package to the client and assigns the resulting **AppvClientPackage** object to the variable $Package.

## PARAMETERS

### -DynamicDeploymentConfiguration
Specifies the path to a dynamic deployment configuration file for the specified App-V package to be added.
The cmdlet uses the dynamic deployment configuration file to override the default configuration provided in the package manifest.

If you do not specify this parameter, the App-V client assigns the default computer policy to the App-V package to be added.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path
Specifies the location of the .appv file containing the package to be added.
This parameter can point to a local directory, a network directory, or an HTTP or HTTPS URL.

```yaml
Type: String
Parameter Sets: (All)
Aliases: PSPath

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.AppvAgent.AppvPackage

## OUTPUTS

### Microsoft.AppvAgent.AppvClientPackage

## NOTES

## RELATED LINKS

[Get-AppvClientPackage](./Get-AppvClientPackage.md)

[Mount-AppvClientPackage](./Mount-AppvClientPackage.md)

[Publish-AppvClientPackage](./Publish-AppvClientPackage.md)

[Publish-AppvClientPackage](./Publish-AppvClientPackage.md)

[Remove-AppvClientPackage](./Remove-AppvClientPackage.md)

[Repair-AppvClientPackage](./Repair-AppvClientPackage.md)

[Set-AppvClientPackage](./Set-AppvClientPackage.md)

[Stop-AppvClientPackage](./Stop-AppvClientPackage.md)

[Unpublish-AppvClientPackage](./Unpublish-AppvClientPackage.md)


