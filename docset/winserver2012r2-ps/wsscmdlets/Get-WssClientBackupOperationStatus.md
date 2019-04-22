---
external help file: WssCmdlets.dll-Help.xml
online version: 
schema: 2.0.0
title: Get-WssClientBackupOperationStatus
description: 
keywords: powershell, cmdlet
author: kenwith
manager: jasgro
ms.date: 2017-12-05
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 4DDE34B9-2074-40B4-A81D-82EB4BF5113E
ms.author: kenwith
ms.reviewer: brianlic
---

# Get-WssClientBackupOperationStatus

## SYNOPSIS
Gets the status of backup-related operations.

## SYNTAX

```
Get-WssClientBackupOperationStatus [<CommonParameters>]
```

## DESCRIPTION
The **Get-WssClientBackupOperationStatus** cmdlet gets the status of backup-related operations for the server.

## EXAMPLES

### Example 1: Get status for backup operations
```
PS C:\> Get-WssClientBackupOperationStatus
```

This command gets the status of backup-related operations for the current server.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.WindowsServerSolutions.DataProtection.PCBackup.BackupUtil.WcfContracts.OperationStatusResponse

## OUTPUTS

### Microsoft.WindowsServerSolutions.DataProtection.PCBackup.BackupUtil.WcfContracts.OperationStatusResponse
This cmdlet generates client backup operation status.

## NOTES

## RELATED LINKS

[Disable-WssClientBackup](./Disable-WssClientBackup.md)

[Enable-WssClientBackup](./Enable-WssClientBackup.md)

[Get-WssClientBackup](./Get-WssClientBackup.md)

[Set-WssClientBackup](./Set-WssClientBackup.md)

[Start-WssClientBackup](./Start-WssClientBackup.md)

[Stop-WssClientBackup](./Stop-WssClientBackup.md)

