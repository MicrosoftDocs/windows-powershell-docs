---
author: Kateyanne
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IIS.Powershell.Commands.dll-Help.xml
keywords: powershell, cmdlet
ms.assetid: 06937FDB-7089-44B9-A9B9-782D6F5DEC14
manager: dansimp
ms.date: 12/20/2016
ms.prod: w10
ms.technology: 
ms.topic: reference
online version: 
schema: 2.0.0
title: Start-IISCommitDelay
ms.author: v-kaunu
ms.reviewer:
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

