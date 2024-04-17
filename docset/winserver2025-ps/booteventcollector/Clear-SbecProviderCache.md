---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: BootEventCollector-help.xml
Module Name: BootEventCollector
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/booteventcollector/clear-sbecprovidercache?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Clear-SbecProviderCache
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

