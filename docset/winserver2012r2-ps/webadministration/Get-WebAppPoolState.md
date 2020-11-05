---
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
Module Name: WebAdministration
online version: 
schema: 2.0.0
title: Get-WebAppPoolState
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: DB6C2AC0-0C2C-4897-A23D-4BA2E92E72B4
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Get-WebAppPoolState

## SYNOPSIS
Gets the run-time state of an IIS application pool.

## SYNTAX

```
Get-WebAppPoolState [[-Name] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-WebAppPoolState** cmdlet gets the run-time state of an Internet Information Services (IIS) application pool.

## EXAMPLES

### Example 1: Get the run-time state of the DefaultAppPool
```
IIS:\>Get-WebAppPoolState -Name "DefaultAppPool"

Value

-----

Started
```

This command gets the run-time state of the DefaultAppPool.

## PARAMETERS

### -Name
Specifies the name of the application pool for which the state is returned.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

