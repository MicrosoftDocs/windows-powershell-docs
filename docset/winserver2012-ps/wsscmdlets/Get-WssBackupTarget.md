---
external help file: WSS_Cmdlets.xml
Module Name: WssCmdlets
online version: https://learn.microsoft.com/powershell/module/wsscmdlets/get-wssbackuptarget?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-WssBackupTarget

## SYNOPSIS
Retrieves all backup targets from a scheduled backup policy.

## SYNTAX

```
Get-WssBackupTarget [-BackupPolicy] <ScheduledBackupPolicy>
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
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-WssBackupTarget](./Add-WssBackupTarget.md)

[New-WssBackupTarget](./New-WssBackupTarget.md)

[Remove-WssBackupTarget](./Remove-WssBackupTarget.md)

