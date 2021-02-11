---
external help file: Microsoft.Msmq.PowerShell.Commands.dll-Help.xml
Module Name: MSMQ
online version: 
schema: 2.0.0
title: Get-MsmqQueueManager
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: DCEC1518-0933-451A-96F6-9BC71FE74A3A
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Get-MsmqQueueManager

## SYNOPSIS
Gets a queue manager.

## SYNTAX

```
Get-MsmqQueueManager [<CommonParameters>]
```

## DESCRIPTION
The **Get-MsmqQueueManager** cmdlet gets a **QueueManager** object.
The **QueueManager** object contains state information for the local queue manager.
The cmdlet gets the properties of the **QueueManager** object by using native Message Queuing (also known as MSMQ) APIs.

## EXAMPLES

### Example 1
```
PS C:\>Get-MsmqQueueManager
```

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Set-MsmqQueueManager](./Set-MsmqQueueManager.md)

