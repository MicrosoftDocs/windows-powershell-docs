---
author: Kateyanne
external help file: WSS_Cmdlets.xml
manager: dansimp
Module Name: WssCmdlets
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/get-wssbackupsystemrecovery?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-WssBackupSystemRecovery

## SYNOPSIS
Gets a bare metal restore option from a scheduled backup policy.

## SYNTAX

```
Get-WssBackupSystemRecovery [-BackupPolicy] <ScheduledBackupPolicy>
```

## DESCRIPTION
The **Get-WssBackupSystemRecovery** cmdlet gets a value that indicates whether a backup policy can perform bare metal restore operations.
It gets this value from a scheduled backup policy.
A bare metal restore operation restores a full operating system, including critical volumes, from a backup.

## EXAMPLES

### Example 1: Get bare metal restore options from a backup policy
```
PS C:\> Get-WssBackupSystemRecovery -BackupPolicy $ContosoBUPolicy25
```

This command gets the bare metal restore option from the scheduled backup policy that is stored in the variable named **$ContosoBUPolicy25**.

## PARAMETERS

### -BackupPolicy
Specifies the scheduled backup policy for which to display information.

```yaml
Type: ScheduledBackupPolicy
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-WssBackupSystemRecovery](./Add-WssBackupSystemRecovery.md)

[Remove-WssBackupSystemRecovery](./Remove-WssBackupSystemRecovery.md)

