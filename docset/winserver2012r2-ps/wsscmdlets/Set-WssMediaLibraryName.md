---
external help file: WssCmdlets.dll-Help.xml
online version: 
schema: 2.0.0
title: Set-WssMediaLibraryName
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 9B539128-39E2-479D-9255-916BE6CE0392
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Set-WssMediaLibraryName

## SYNOPSIS
Changes the name of the Media Library.

## SYNTAX

```
Set-WssMediaLibraryName [-MediaLibraryName] <String> [<CommonParameters>]
```

## DESCRIPTION
The **Set-WssMediaLibraryName** cmdlet changes the name of the Media Library for the current server.
You can use the Get-WssMediaLibraryName cmdlet to see the Media Library name.

## EXAMPLES

### Example 1: Rename a Media Library
```
PS C:\> Set-WssMediaLibraryName -MediaLibraryName "Accounting Library"
```

This command gives the Media Library the name Accounting Library.

## PARAMETERS

### -MediaLibraryName
Specifies a new name for the Media Library shared by the server.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-WssMediaLibraryName](./Get-WssMediaLibraryName.md)

