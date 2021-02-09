---
external help file: Microsoft.HCS.Management.dll-Help.xml
online version: 
schema: 2.0.0
title: Get-HcsUpdateStatus
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: D05848E5-D719-4B5D-8E3F-BBE0B451C187
---

# Get-HcsUpdateStatus

## SYNOPSIS
Gets the current status of updates.

## SYNTAX

```
Get-HcsUpdateStatus [<CommonParameters>]
```

## DESCRIPTION
The **Get-HcsUpdateStatus** cmdlet gets the current status of updates.
The cmdlet provides the timestamp of the last update, indicates whether any updates are in progress, and provides any errors that occurred after the last successful update.

## EXAMPLES

### Example 1: Get status of updates
```
PS C:\>Get-HcsUpdateStatus
```

This command gets the current status of updates on your device.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.HCS.Management.Patching.HcsUpdateStatus
The HcsUpdateStatus object has the following properties:

- RunInprogress 
- DateTime LastHotfixTimestamp 
- DateTime LastUpdateTimestamp 
- IEnumerable\<HcsUpdateEvent\> Controller0Events 
- IEnumerable\<HcsUpdateEvent\> Controller1Events

## NOTES

## RELATED LINKS

[Get-HcsUpdateAvailability](./Get-HcsUpdateAvailability.md)

[Start-HcsUpdate](./Start-HcsUpdate.md)

[Start-HcsHotfix](./Start-HcsHotfix.md)

