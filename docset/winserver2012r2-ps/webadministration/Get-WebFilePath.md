---
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
Module Name: WebAdministration
online version: 
schema: 2.0.0
title: Get-WebFilePath
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 2664F7E9-259B-4179-A247-7E1943CB3D21
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Get-WebFilePath

## SYNOPSIS
Gets the physical path to the location of the specified IIS module.

## SYNTAX

```
Get-WebFilePath [[-PSPath] <String[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-WebFilePath** cmdlet gets the physical path to the location of the specified Internet Information Services (IIS) module.

## EXAMPLES

### Example 1: Get the physical path of the default website
```
IIS:\>Get-WebFilePath -PSPath 'IIS:\Sites\Default Web Site'
Directory: Microsoft.PowerShell.Core\FileSystem::C:\inetpub

Mode    LastWriteTime        Length    Name
----    -------------        ------    ----
d----   7/28/2008 9:40 PM              wwwroot
```

This command retrieves the physical path for the default website.

## PARAMETERS

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

