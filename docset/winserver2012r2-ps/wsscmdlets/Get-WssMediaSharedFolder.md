---
external help file: WssCmdlets.dll-Help.xml
online version: 
schema: 2.0.0
title: Get-WssMediaSharedFolder
description: 
keywords: powershell, cmdlet
author: kenwith
manager: jasgro
ms.date: 2017-12-05
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 5A68C6C7-30DD-4564-811A-AE8967340503
ms.manager: dansimp
ms.author: kenwith
ms.reviewer: brianlic
---

# Get-WssMediaSharedFolder

## SYNOPSIS
Gets the shared folders included in the Media Library.

## SYNTAX

```
Get-WssMediaSharedFolder [<CommonParameters>]
```

## DESCRIPTION
The **Get-WssMediaSharedFolder** cmdlet gets the shared folders included in the Media Library.

## EXAMPLES

### Example 1: Get shared folders
```
PS C:\> Get-WssMediaSharedFolder
```

This command gets the shared folders included in the Medial Library.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.WindowsServerSolutions.MediaStreaming.MediaStreamingSharedFolder
This cmdlet generates a shared folder object with information specific to media.

## NOTES

## RELATED LINKS

[Set-WssMediaLibraryInclusion](./Set-WssMediaLibraryInclusion.md)

[Get-WssMediaServerEnabled](./Get-WssMediaServerEnabled.md)

[Get-WssMediaLibraryName](./Get-WssMediaLibraryName.md)

