---
external help file: WssCmdlets.dll-Help.xml
online version: 
schema: 2.0.0
title: Get-WssGlobalClientBackupPolicy
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 922D994A-079B-4C5A-84C7-5CC28688F240
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Get-WssGlobalClientBackupPolicy

## SYNOPSIS
Gets the current global client backup policy.

## SYNTAX

```
Get-WssGlobalClientBackupPolicy [<CommonParameters>]
```

## DESCRIPTION
The **Get-WssGlobalClientBackupPolicy** cmdlet gets the current global client backup policy.
This policy includes the following values: 

- BackupStartTime.
The beginning of the backup window.
The default value is 18:00.
- BackupEndTime.
The end of the backup window.
The default value is 9:00.
- DailyRetainCount.
The number of daily backups to keep.
The default value is five. 
- WeeklyRetainCount.
The number of weekly backups to keep.
The default value is four.
- MonthlyRetainCount.
The number of monthly backups to keep.
The default value is six. 
- YearlyRetainCount.
The number of yearly backups to keep.
The default value is ten.

You can use the Set-WssGlobalClientBackupPolicy cmdlet to change any of these settings, or to reset all settings to their default values.

## EXAMPLES

### Example 1: Get the global client backup policy
```
PS C:\> Get-WssGlobalClientBackupPolicy
```

This command gets the global client backup policy.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.WindowsServerSolutions.DataProtection.PCBackup.BackupUtil.WcfContracts.PCBackupConfiguration

## OUTPUTS

### Microsoft.WindowsServerSolutions.DataProtection.PCBackup.BackupUtil.WcfContracts.PCBackupConfiguration
This cmdlet generates the PC backup configuration.

## NOTES

## RELATED LINKS

[Set-WssGlobalClientBackupPolicy](./Set-WssGlobalClientBackupPolicy.md)

