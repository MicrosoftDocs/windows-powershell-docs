---
external help file: WssCmdlets.dll-Help.xml
online version: 
schema: 2.0.0
title: Repair-WssMediaStreamingMetadata
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: C94D8EAA-BE45-469B-84C6-3C4E94299458
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Repair-WssMediaStreamingMetadata

## SYNOPSIS
Repairs the database that stores information for media streaming.

## SYNTAX

```
Repair-WssMediaStreamingMetadata [<CommonParameters>]
```

## DESCRIPTION
The **Repair-WssMediaStreamingMetadata** cmdlet repairs the database that stores information for media streaming.
Use this cmdlet only when you see symptoms of data corruption.

## EXAMPLES

### Example 1: Repair media streaming metadata
```
PS C:\>Repair-WssMediaStreamingMetadata
```

This command repairs the database that contains media streaming metadata.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-WssMediaLibraryName](./Get-WssMediaLibraryName.md)

[Set-WssMediaLibraryName](./Set-WssMediaLibraryName.md)

