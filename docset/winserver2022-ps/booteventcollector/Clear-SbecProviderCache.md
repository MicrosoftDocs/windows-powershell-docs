---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-kaunu
author: Kateyanne
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: BootEventCollector-help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: 
ms.topic: reference
online version: 
schema: 2.0.0
title: Clear-SbecProviderCache
ms.reviewer:
ms.assetid: 874EA74D-7B1A-4454-9865-1802D5AEF5C9
---

# Clear-SbecProviderCache

## SYNOPSIS
Clears the provider cache.

## SYNTAX

```
Clear-SbecProviderCache [<CommonParameters>]
```

## DESCRIPTION
The **Clear-SbecProviderCache** cmdlet clears the provider cache.

The next time you run the **Get-SbecTraceProviders** cmdlet, the cmdlet re-reads the providers from the operating system and re-populates the cache.

## EXAMPLES


## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None.

## OUTPUTS

### None.

## NOTES

## RELATED LINKS

[Get-SbecTraceProviders](./Get-SbecTraceProviders.md)

