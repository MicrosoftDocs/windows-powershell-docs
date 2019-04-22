---
ms.technology: powershell-mdop
ms.mktglfcycl: manage
ms.author: kenwith
ms.prod: w10
ms.sitesec: library
author: kenwith
description: Use this topic to help manage MDOP technologies with Windows PowerShell.
external help file: Microsoft.AppV.AppVClientPowerShell.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro 
ms.assetid: E1F1F2D1-AC0E-4DB6-904C-CCE50F743CC7
ms.date: 2016-12-05
ms.devlang: powershell
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-AppvClientConfiguration
---

# Get-AppvClientConfiguration

## SYNOPSIS
Returns the configuration for the App-V client.

## SYNTAX

```
Get-AppvClientConfiguration [[-Name] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AppvClientConfiguration** cmdlet returns an object containing all of the settings and permissions for the Microsoft Application Virtualization (App-V) client.
These settings include both App-V client settings and permissions.

In the case where a particular setting is asked for, the cmdlet will return the value for that specific setting.

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
Not Specified.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.AppV.AppvClientPowerShell.AppvClientConfiguration
In you do not specify any parameters, the cmdlet returns an **AppvClientConfiguration** object.
The object is displayed as a two column table.
The first column contains the specific configuration and the second column contains the associated current value.

If you specify the *Name* parameter, the cmdlet returns the same two column table, but only for the configuration requested.

## NOTES

## RELATED LINKS

[Set-AppvClientConfiguration](./Set-AppvClientConfiguration.md)


