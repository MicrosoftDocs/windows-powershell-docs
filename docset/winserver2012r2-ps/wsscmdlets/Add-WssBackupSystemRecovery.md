---
external help file: WssCmdlets.dll-Help.xml
online version: 
schema: 2.0.0
title: Add-WssBackupSystemRecovery
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: F5043B28-1212-4C0F-802C-E26EBECD8576
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Add-WssBackupSystemRecovery

## SYNOPSIS
Adds a bare metal recovery option to a scheduled backup policy.

## SYNTAX

```
Add-WssBackupSystemRecovery [-BackupPolicy] <ScheduledBackupPolicy> [<CommonParameters>]
```

## DESCRIPTION
The **Add-WssBackupSystemRecovery** cmdlet adds a bare metal recovery option to a scheduled backup policy.
Use a backup policy with a full metal recovery option to recover the full operating system, including critical volumes, from the backup.

## EXAMPLES

### Example 1: Add a bare metal recovery option to a backup policy
```
PS C:\>$ContosoBUPolicy25 = Get-WssBackupPolicy
PS C:\> Add-WssBackupSystemRecovery -BackupPolicy $ContosoBUPolicy25
```

This command adds a bare metal recovery option to a backup policy.

The first command gets the backup policy for the computer and stores it in the variable named **$ContosoBUPolicy25**.

The second command adds bare metal recovery to the backup policy that is stored in **$ContosoBUPolicy25**.

## PARAMETERS

### -BackupPolicy
Specifies the scheduled backup policy to which to add the option for bare metal recovery.

```yaml
Type: ScheduledBackupPolicy
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.WindowsServerSolutions.DataProtection.ServerBackup.ObjectModel.ScheduledBackupPolicy
This cmdlet returns the BackupPolicy parameter.

## NOTES

## RELATED LINKS

[Get-WssBackupSystemRecovery](./Get-WssBackupSystemRecovery.md)

[Remove-WssBackupSystemRecovery](./Remove-WssBackupSystemRecovery.md)

