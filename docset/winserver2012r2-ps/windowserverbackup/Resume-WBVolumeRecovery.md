---
external help file: wsbcmdlet.dll-Help.xml
Module Name: WindowsServerBackup
online version: 
schema: 2.0.0
title: Resume-WBVolumeRecovery
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: F4AF6DD5-285C-41E2-9B4A-CC5AEFF0CDE6
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Resume-WBVolumeRecovery

## SYNOPSIS
Resumes a volume recovery operation from a removable device and specific media.

## SYNTAX

```
Resume-WBVolumeRecovery [<CommonParameters>]
```

## DESCRIPTION
The **Resume-WBVolumeRecovery** cmdlet resumes a volume recovery operation performed from a removable device and specific media.
If the requested media is not inserted, the cmdlet returns an error with a description of the requested media.
Otherwise, the cmdlet returns confirmation that the recovery operation resumed.

## EXAMPLES

### Example 1: Resume a volume recovery operation
```
PS C:\> Resume-WBVolumeRecovery
```

This command resumes the volume recovery operation.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### System.String, System.Exception
If the requested media is not inserted, the cmdlet returns an error with the description of the requested media.
Otherwise, the recovery operation resumes and the cmdlet returns a confirmation message.

## NOTES

## RELATED LINKS

[Start-WBVolumeRecovery](./Start-WBVolumeRecovery.md)

