---
external help file: WssCmdlets.dll-Help.xml
online version: 
schema: 2.0.0
title: Get-WssBackupDisk
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: C23AC990-B422-4923-B01F-07D3C7E49D1F
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Get-WssBackupDisk

## SYNOPSIS
Gets a list of online hard disks that can be backup targets and can store server backups..

## SYNTAX

```
Get-WssBackupDisk [<CommonParameters>]
```

## DESCRIPTION
The **Get-WssBackupDisk** cmdlet gets all online hard disks that can be  backup targets and can store server backups.

## EXAMPLES

### Example 1: Get a list of backup targets
```
PS C:\> $ContosoBUDisk215 = Get-WssBackupDisk
```

This command gets the list of currently available backup targets and stores the list in the variable named $ContosoBUDisk215.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.WindowsServerSolutions.DataProtection.ServerBackup.ObjectModel.BackupDisk
This cmdlet returns the disks which can be used as server backup targets.

## NOTES

## RELATED LINKS

[Initialize-WssBackupDisk](./Initialize-WssBackupDisk.md)

