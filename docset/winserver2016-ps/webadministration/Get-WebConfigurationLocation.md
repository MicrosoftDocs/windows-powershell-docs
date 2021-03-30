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
title: Get-WebConfigurationLocation
ms.reviewer:
ms.assetid: A0C732EB-6D51-45C2-BDAF-144305A59E83
---

# Get-WebConfigurationLocation

## SYNOPSIS
Gets the location of a configuration setting.

## SYNTAX

```
Get-WebConfigurationLocation [[-Name] <String>] [-Recurse] [[-PSPath] <String[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-WebConfigurationLocation** cmdlet gets the location of a specified configuration setting.

## EXAMPLES

### Example 1: Get location tags
```
IIS:\> Get-WebConfigurationLocation
```

This command returns all locations that are configured by using location tags.

## PARAMETERS

### -Name
Specifies the name of the configuration location.
If you do not specify this parameter, this cmdlet gets all locations.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PSPath
Specifies an IIS configuration path to the location.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Recurse
Indicates that this cmdlet returns locations within the hierarchy of the specified location.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Remove-WebConfigurationLocation](./Remove-WebConfigurationLocation.md)

[Rename-WebConfigurationLocation](./Rename-WebConfigurationLocation.md)

