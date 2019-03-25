---
external help file: WssCmdlets.dll-Help.xml
online version: 
schema: 2.0.0
title: Test-WssHealth
description: 
keywords: powershell, cmdlet
author: kenwith
manager: jasgro
ms.date: 2017-12-05
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 8CE2BB10-E6EB-4C19-9962-775FC951E566
ms.author: kenwith
ms.reviewer: brianlic
---

# Test-WssHealth

## SYNOPSIS
Performs an evaluation of all health checks.

## SYNTAX

```
Test-WssHealth [<CommonParameters>]
```

## DESCRIPTION
The **Test-WssHealth** cmdlet performs an evaluation of all health checks.
If the cmdlet finds no outstanding health alerts, it returns a value of $True.
If it finds outstanding health alerts, it returns a value of $False.

## EXAMPLES

### Example 1: Perform a health check evaluation
```
PS C:\> Test-WssHealth
```

This command performs evaluation of all health checks.
The command returns a value of $True or $False, depending on whether it finds outstanding alerts.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Boolean

## NOTES

## RELATED LINKS

