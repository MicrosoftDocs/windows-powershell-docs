---
external help file: WssCmdlets.dll-Help.xml
online version: 
schema: 2.0.0
title: Stop-WssClientBackupRepair
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 6140668B-3853-472F-95A0-939F64D7455F
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Stop-WssClientBackupRepair

## SYNOPSIS
Stops the attempt to repair a database of client computer backups.

## SYNTAX

```
Stop-WssClientBackupRepair [<CommonParameters>]
```

## DESCRIPTION
The **Stop-WssClientBackupRepair** cmdlet stops the attempt to repair the database of client computer backups.
You can use the Start-WssClientBackupRepair cmdlet to start an attempt to repair a database that is corrupt or unusable.

## EXAMPLES

### Example 1: Stop a client backup database repair
```
PS C:\> Stop-WssClientBackupRepair
```

This command stops the attempt to repair the client backup database.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Start-WssClientBackupRepair](./Start-WssClientBackupRepair.md)

[Enable-WssClientBackup](./Enable-WssClientBackup.md)

