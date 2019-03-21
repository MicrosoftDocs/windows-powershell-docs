---
external help file: OnlineBackup_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: kenwith
author: kenwith
ms.assetid: 136C3DCD-179C-44E6-9648-43191CF477FC
ms.manager: dansimp
---

# New-OBSchedule

## SYNOPSIS
Creates a new OBSchedule object based on the days of the week and times of day to create daily backups.

## SYNTAX

```
New-OBSchedule
 [[-DaysOfWeek] <DayOfWeek[]{Sunday | Monday | Tuesday | Wednesday | Thursday | Friday | Saturday}>]
 [[-TimesOfDay] <TimeSpan[]>]
```

## DESCRIPTION
The **New-OBSchedule** cmdlet creates a new OBSchedule object which specifies the when the backup should happen in terms of the days of the week and times of the day.
By default the schedule is created at 9:00PM every Sunday.

ps_mob_user_group_remark

## EXAMPLES

### EXAMPLE 1
```
PS C:\> New-OBSchedule -DaysOfWeek Sunday,Monday,Tuesday,Wednesday,Thursday,Friday,Saturday -TimesOfDay 12:00,16:00
```

This example creates a schedule for backup.

## PARAMETERS

### -DaysOfWeek
Specifies the days of the week on which backup should run.
The following values are supported for this parameter - "Sunday", "Monday", "Tuesday", "Wednesday", "Thursday", "Friday" and "Saturday".

```yaml
Type: DayOfWeek[]{Sunday | Monday | Tuesday | Wednesday | Thursday | Friday | Saturday}
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TimesOfDay
Specifies the times of the day during which backup should run.

```yaml
Type: TimeSpan[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

### None

## OUTPUTS

### Microsoft.Internal.CloudBackup.Commands.OBSchedule

## NOTES

## RELATED LINKS

[Get-OBPolicy](./Get-OBPolicy.md)

[Get-OBSchedule](./Get-OBSchedule.md)

[New-OBFileSpec](./New-OBFileSpec.md)

[New-OBPolicy](./New-OBPolicy.md)

[New-OBRetentionPolicy](./New-OBRetentionPolicy.md)

[Set-OBSchedule](./Set-OBSchedule.md)

