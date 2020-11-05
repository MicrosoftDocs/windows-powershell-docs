---
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
Module Name: WebAdministration
online version: 
schema: 2.0.0
title: Get-WebConfigFile
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 60345A39-C114-44AC-89F3-ABCCA70483EA
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Get-WebConfigFile

## SYNOPSIS
Gets the file system path of the web.config file.

## SYNTAX

```
Get-WebConfigFile [[-PSPath] <String[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-WebConfigFile** cmdlet gets the physical path of the Internet Information Services (IIS) configuration file at the specified IIS module namespace path.

## EXAMPLES

### Example 1: Open the Web.config file for the default website
```
IIS:\>Notepad (Get-WebConfigFile -PSPath 'IIS:\Sites\Default Web Site')
```

This command uses Notepad to open the web.config file for the default website.

## PARAMETERS

### -PSPath
Specifies the IIS module namespace path to the site that contains the Web.config file.

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

