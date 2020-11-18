---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-kaunu
author: Kateyanne
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/27/2016
ms.prod: w10
ms.technology: 
ms.topic: reference
online version: 
schema: 2.0.0
title: Select-WebConfiguration
ms.reviewer:
ms.assetid: BF044083-1E9F-49E7-8CBE-E44B43DC57E7
---

# Select-WebConfiguration

## SYNOPSIS
Returns IIS configuration objects.

## SYNTAX

```
Select-WebConfiguration [-Filter] <String[]> [<CommonParameters>]
```

## DESCRIPTION
The **Select-WebConfiguration** cmdlet returns information about Internet Information Services (IIS) configuration objects.

## EXAMPLES

### Example 1: Get configuration settings
```
IIS:\> Select-WebConfiguration -Filter "get-config(MACHINE/WEBROOT/APPHOST/testSite)/appSettings"
```

This command returns the configuration collection from the appSettings location.
If the specified location does not exist, the cmdlet returns an error.

## PARAMETERS

### -Filter
Specifies an XPath filter expression.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-WebConfiguration](./Add-WebConfiguration.md)

[Backup-WebConfiguration](./Backup-WebConfiguration.md)

[Clear-WebConfiguration](./Clear-WebConfiguration.md)

[Get-WebConfiguration](./Get-WebConfiguration.md)

[Restore-WebConfiguration](./Restore-WebConfiguration.md)

[Set-WebConfiguration](./Set-WebConfiguration.md)

