---
external help file: OnlineBackup_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: kenwith
author: kenwith
ms.assetid: 3F5386E3-4AD6-43DF-BE21-9837265355C3
manager: dansimp
---

# Set-OBSchedule

## SYNOPSIS
Sets the OBSchedule object, which includes the days of the week and times of day to create daily backups, for the backup policy (OBPolicy object).

## SYNTAX

```
Set-OBSchedule [-Policy] <CBPolicy> [-Schedule] <CBSchedule> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Set-OBSchedule** cmdlet sets the OBSchedule object, which includes the days of the week and times of day to create daily backups, for the backup policy (OBPolicy object).

This cmdlet sets the OBPolicy object with references to the days of the week and times of day to create backups.

This cmdlet supports WhatIf and Confirm parameters with a medium impact.
The medium impact signifies that the cmdlet will not prompt the user for confirmation by default.
The WhatIf parameter gives a verbose description of what the cmdlet does without performing any operation.
The Confirm parameter specifies whether the cmdlet should prompt the user.
Using -Confirm:$FALSE will override the prompt.

ps_mob_user_group_remark

## EXAMPLES

### EXAMPLE 1
```
PS C:\>$policy = Get-OBPolicy



PS C:\>Get-OBSchedule $policy | Set-OBSchedule $policy
```

This example sets a protection policy.

### EXAMPLE 2
```
PS C:\>$sch = New-OBSchedule -DaysOfWeek Sunday,Monday,Tuesday,Wednesday,Thursday,Friday,Saturday -TimesOfDay 12:00,16:00,20:00



PS C:\>New-OBPolicy | Set-OBSchedule -Schedule $sch
```

This example sets a new protection policy.

## PARAMETERS

### -Policy
Specifies the policy which the schedule is being set.

```yaml
Type: CBPolicy
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Schedule
Specifies the schedule to be set for the policy.

```yaml
Type: CBSchedule
Parameter Sets: (All)
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

### None

## OUTPUTS

### Microsoft.Internal.CloudBackup.Client.Cmdlets.OBPolicy

## NOTES

## RELATED LINKS

[Get-OBPolicy](./Get-OBPolicy.md)

[Get-OBSchedule](./Get-OBSchedule.md)

[New-OBPolicy](./New-OBPolicy.md)

[New-OBSchedule](./New-OBSchedule.md)

