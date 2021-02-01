---
external help file: WssCmdlets.dll-Help.xml
online version: 
schema: 2.0.0
title: Get-WssBackupPolicy
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: A8231A90-0A08-46D7-A01F-FC691605B16D
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Get-WssBackupPolicy

## SYNOPSIS
Gets the current scheduled backup policy.

## SYNTAX

```
Get-WssBackupPolicy [<CommonParameters>]
```

## DESCRIPTION
The **Get-WssBackupPolicy** cmdlet gets the current scheduled backup policy.
The cmdlet returns an empty scheduled backup policy if no backup policy is configured.

## EXAMPLES

### Example 1 Get the current scheduled backup policy
```
PS C:\> $ContosoBUPol12 = Get-WssBackupPolicy
```

This command gets the currently scheduled backup policy and stores it in the **$ContosoBUPol12** variable.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.WindowsServerSolutions.DataProtection.ServerBackup.ObjectModel.ScheduledBackupPolicy
This cmdlet returns the server backup policy that specifies backup options such as backup targets, backup volume and schedule time.

## NOTES

## RELATED LINKS

[Disable-WssBackupPolicy](./Disable-WssBackupPolicy.md)

[Resume-WssBackupPolicy](./Resume-WssBackupPolicy.md)

[Set-WssBackupPolicy](./Set-WssBackupPolicy.md)

[Suspend-WssBackupPolicy](./Suspend-WssBackupPolicy.md)

