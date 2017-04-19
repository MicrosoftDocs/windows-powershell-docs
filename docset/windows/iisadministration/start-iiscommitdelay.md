---
author: brianlic-msft
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IIS.Powershell.Commands.dll-Help.xml
keywords: powershell, cmdlet
manager: alanth
ms.assetid: 06937FDB-7089-44B9-A9B9-782D6F5DEC14
ms.author: brianlic
ms.date: 2016-12-20
ms.mktglfcycl: manage
ms.prod: w10
ms.sitesec: library
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Start-IISCommitDelay
---

# Start-IISCommitDelay

## SYNOPSIS
Instructs the IIS configuration system to delay the commitment of changes.

## SYNTAX

```
Start-IISCommitDelay [<CommonParameters>]
```

## DESCRIPTION
The **Start-IISCommitDelay** cmdlet instructs the Internet Information Services (IIS) configuration system to delay the commitment of changes.
The commitment of changes is delayed until the **Stop-IISCommitDelay** cmdlet is executed.

## EXAMPLES

### Example 1: Delay the commit of changes
```
PS C:\> Start-IISCommitDelay
```

This command delays the modification of IIS configuration settings until the **Stop-IISCommitDelay** cmdlet is executed.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Stop-IISCommitDelay](./Stop-IISCommitDelay.md)

[IIS Administration Cmdlets for Windows PowerShell](./iisadministration.md)

