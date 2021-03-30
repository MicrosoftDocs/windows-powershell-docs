---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-kaunu
author: Kateyanne
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.AppV.AppVClientPowerShell.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: 
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-AppvClientConfiguration
ms.reviewer:
ms.assetid: 2487C6CC-6433-4C9C-A830-40832F9D62F8
---

# Get-AppvClientConfiguration

## SYNOPSIS
Returns the configuration for the App-V client.

## SYNTAX

```
Get-AppvClientConfiguration [[-Name] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AppvClientConfiguration** cmdlet returns an object that contains all of the settings and permissions for the Microsoft Application Virtualization (App-V) client.
These settings include both App-V client settings and permissions.

If a particular setting is specified, the cmdlet returns the value for that setting.

## EXAMPLES

### Example 1: Display all configuration settings
```
PS C:\> Get-AppvClientConfiguration
```

This command displays all of the App-V Client Configuration settings.

### Example 2: Display a single configuration setting
```
PS C:\> Get-AppvClientConfiguration -Name "PackageSourceRoot"
```

This command displays the value of the **PackageSourceRoot** setting.

## PARAMETERS

### -Name
Specifies the name of a setting.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.AppV.AppvClientPowerShell.AppvClientConfiguration
The cmdlet returns an **AppvClientConfiguration** object, if you do not specify the *Name* parameter.
The object is displayed as a two column table.
The first column contains the specific configuration and the second column contains the associated current value.

If you specify *Name*, the cmdlet returns the same two column table, but only for the configuration requested.

## NOTES

## RELATED LINKS

[Set-AppvClientConfiguration](./Set-AppvClientConfiguration.md)

