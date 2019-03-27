---
external help file: StorSpaces2_Cmdlets.xml
online version: 
schema: 2.0.0
title: New-StorageSpacesEventLog
description: 
keywords: powershell, cmdlet
author: kenwith
manager: jasgro
ms.date: 2017-10-30
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: EA39675F-A51D-4626-9224-B96ECD93C36A
ms.author: kenwith
ms.reviewer: brianlic
---

# New-StorageSpacesEventLog

## SYNOPSIS
Enables logging of notifications for Storage Spaces.

## SYNTAX

```
New-StorageSpacesEventLog
```

## DESCRIPTION
The New-StorageSpacesEventLog cmdlet creates an event log under Applications and Services logs in Event Viewer named StorageSpaces Events, and creates a scheduled job in Windows PowerShell to monitor for events and log them to this event log.

This cmdlet requires administrative privileges and you must restart the computer before logging begins.

## EXAMPLES

### Example 1 - Enable logging for Storage Spaces
```
PS C:\>New-StorageSpacesEventLog
```

## PARAMETERS

## INPUTS

### None

## OUTPUTS

### Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition
This cmdlet outputs an object that represents the scheduled job created to monitor for Storage Spaces events.

## NOTES

## RELATED LINKS

