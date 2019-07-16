---
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
Module Name: WebAdministration
online version: 
schema: 2.0.0
title: Get-WebConfigurationLocation
description: 
keywords: powershell, cmdlet
author: andreabarr
manager: jasgro
ms.date: 2017-10-30
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: A0C732EB-6D51-45C2-BDAF-144305A59E83
ms.author: v-anbarr
ms.reviewer: brianlic
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
IIS:\>Get-WebConfigurationLocation
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Remove-WebConfigurationLocation](./Remove-WebConfigurationLocation.md)

[Rename-WebConfigurationLocation](./Rename-WebConfigurationLocation.md)

