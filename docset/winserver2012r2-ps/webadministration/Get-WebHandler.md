---
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
Module Name: WebAdministration
online version: 
schema: 2.0.0
title: Get-WebHandler
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 8E74C047-54C0-4736-8145-54E6B7201EA8
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Get-WebHandler

## SYNOPSIS
Gets IIS request handlers.

## SYNTAX

```
Get-WebHandler [[-Name] <String>] [-Location <String[]>] [[-PSPath] <String[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-WebHandler** cmdlet gets Internet Information Services (IIS) request handlers.
If you specify the **Name** parameter, information is returned for the specified handler.

## EXAMPLES

### Example 1: Get the handler section
```
IIS:\>Get-WebHandler -PSPath 'IIS:\Sites\Default Web Site'
```

This command gets handlers configured for the default website.

## PARAMETERS

### -Location
Specifies the location for which the cmdlet returns handler information.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the name of a handler to get.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PSPath
Specifies an IIS configuration path.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[New-WebHandler](./New-WebHandler.md)

[Remove-WebHandler](./Remove-WebHandler.md)

[Set-WebHandler](./Set-WebHandler.md)

