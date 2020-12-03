---
external help file: WSS_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: 8E202634-15CB-436F-B240-041991ACFB81
manager: dansimp
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

