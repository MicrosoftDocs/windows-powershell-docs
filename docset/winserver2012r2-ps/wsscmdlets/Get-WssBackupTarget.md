---
external help file: WssCmdlets.dll-Help.xml
online version: 
schema: 2.0.0
title: Get-WssBackupTarget
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 8E202634-15CB-436F-B240-041991ACFB81
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Get-WssBackupTarget

## SYNOPSIS
Retrieves all backup targets from a scheduled backup policy.

## SYNTAX

```
Get-WssBackupTarget [-BackupPolicy] <ScheduledBackupPolicy> [<CommonParameters>]
```

## DESCRIPTION
The **Get-WssBackupTarget** cmdlet retrieves all backup targets from a scheduled backup policy.
A scheduled backup policy is a backup file specification that has a backup schedule associated with it.

## EXAMPLES

### Example 1: Get all backup targets from a scheduled backup policy
```
PS C:\> Get-WssBackupTarget -BackupPolicy $ContosoBUPolicy213
```

This command gets all backup targets from the backup policy that is stored in the variable named **$ContosoBUPolicy213**.

## PARAMETERS

### -BackupPolicy
Specifies the scheduled backup policy from which to retrieve the backup target.

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

### Microsoft.WindowsServerSolutions.DataProtection.ServerBackup.ObjectModel.BackupTarget
This cmdlet returns a list of backup targets.

## NOTES

## RELATED LINKS

[Add-WssBackupTarget](./Add-WssBackupTarget.md)

[New-WssBackupTarget](./New-WssBackupTarget.md)

[Remove-WssBackupTarget](./Remove-WssBackupTarget.md)

