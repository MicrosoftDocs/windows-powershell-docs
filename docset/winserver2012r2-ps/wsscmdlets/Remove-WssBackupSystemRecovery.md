---
external help file: WssCmdlets.dll-Help.xml
online version: 
schema: 2.0.0
title: Remove-WssBackupSystemRecovery
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 8746A218-B3BC-4FBB-8258-4393D157426D
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Remove-WssBackupSystemRecovery

## SYNOPSIS
Removes a bare metal recovery option from a scheduled backup policy.

## SYNTAX

```
Remove-WssBackupSystemRecovery [-BackupPolicy] <ScheduledBackupPolicy> [<CommonParameters>]
```

## DESCRIPTION
The **Remove-WssBackupSystemRecovery** cmdlet removes a bare metal recovery option from a scheduled backup policy.
If you remove bare metal recovery from a scheduled backup policy, disaster recovery may not be possible.

## EXAMPLES

### Example 1: Remove a bare metal recovery option from a backup policy
```
PS C:\> Remove-WssBackupSystemRecovery -BackupPolicy $ContosoBUPolicy25
```

This command removes a bare metal recovery option from the backup policy that is stored in the variable named **$ContosoBUPolicy25**.

## PARAMETERS

### -BackupPolicy
Specifies the scheduled backup policy from which to remove the system recovery option.

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
This cmdlet generates the **BackupPolicy** parameter value.

## NOTES

## RELATED LINKS

[Add-WssBackupSystemRecovery](./Add-WssBackupSystemRecovery.md)

[Get-WssBackupSystemRecovery](./Get-WssBackupSystemRecovery.md)

