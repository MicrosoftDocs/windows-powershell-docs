---
external help file: OnlineBackup_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-anbarr
author: andreabarr
ms.assetid: CC58A2E5-286A-4819-AB6A-DBD6C970A457
manager: dansimp
---

# New-OBRetentionPolicy

## SYNOPSIS
Creates a new OBRetentionPolicy specifying the number of days that the backup needs to be retained.

## SYNTAX

```
New-OBRetentionPolicy [[-RetentionDays] <Long {7 | 15 | 30}>] [[-RetentionWeeklyPolicy]] [[-WeekDaysOfWeek] {Sunday | Monday | Tuesday | Wednesday | Thursday | Friday | Saturday}] [[-WeekTimesOfDay] <List[timespan]>] [[-RetentionWeeks] <long>] [[-RetentionMonthlyPolicy]] [<CommonParameters>]
```

## DESCRIPTION
The **New-OBRetentionPolicy** creates a new OBRetentionPolicy object specifying the number of days to retain the backed up items.

ps_mob_user_group_remark

## EXAMPLES

### EXAMPLE 1
```
PS C:\> New-OBRetentionPolicy -RetentionDays 30
```

This example creates a new retention policy.

## PARAMETERS

### -RetentionDays
Specifies the number of days to retain the backup data.
Retention days must be specified as either `7`, `15`, or `30`.
Other integers are not supported.

```yaml
Type: Long {7 | 15 | 30}
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

### None

## OUTPUTS

### Microsoft.Internal.CloudBackup.Commands.OBRetentionPolicy
Specifies the number of days that the backup needs to be retained.

## NOTES

## RELATED LINKS

[Get-OBRetentionPolicy](./Get-OBRetentionPolicy.md)

[Set-OBRetentionPolicy](./Set-OBRetentionPolicy.md)

[New-OBPolicy](./New-OBPolicy.md)

