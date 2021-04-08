---
author: Kateyanne
description: 
external help file: Microsoft.HCS.Management.dll-Help.xml
manager: jasgro
Module Name: HCS
ms.author: v-kaunu
ms.date: 12/05/2017
ms.prod: powershell
ms.reviewer: brianlic
ms.topic: reference
online version: https://docs.microsoft.com/powershell/module/hcs/get-hcsupdatestatus?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-HcsUpdateStatus
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

