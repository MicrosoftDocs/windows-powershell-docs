---
author: brianlic-msft
description: 
external help file: Microsoft.Msmq.PowerShell.Commands.dll-Help.xml
keywords: powershell, cmdlet
manager: alanth
ms.date: 2016-12-27
ms.prod: powershell
ms.technology: powershell
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-MsmqQueueManager
ms.assetid: DCEC1518-0933-451A-96F6-9BC71FE74A3A
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

### Example 1: Get the queue manager
```
PS C:\>Get-MsmqQueueManager
```

This command gets the queue manager.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Set-MsmqQueueManager](./Set-MsmqQueueManager.md)

