---
external help file: WssCmdlets.dll-Help.xml
Module Name: WSSCmdlets
ms.date: 12/05/2017
online version: https://learn.microsoft.com/powershell/module/wsscmdlets/get-wssbackuptarget?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WssBackupTarget
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

