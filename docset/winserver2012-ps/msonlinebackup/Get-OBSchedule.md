---
external help file: OnlineBackup_Cmdlets.xml
online version: 
schema: 2.0.0
ms.assetid: C178CF8E-932E-42CE-831A-1D6450C33437
---

# Get-OBSchedule

## SYNOPSIS
Gets the OBSchedule object, which includes the days of the week and times of day to create daily backups, for the specified OBPolicy object.

## SYNTAX

```
Get-OBSchedule [-Policy] <CBPolicy>
```

## DESCRIPTION
The **Get-OBSchedule** cmdlet gets the current schedule for backups in the backup policy (OBPolicy object).
Backups are run at the times specified in the schedule.
To change the schedule, use the Set-OBSchedule cmdlet.

ps_mob_user_group_remark

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-OBPolicy | Get-OBSchedule
```

This example gets a schedule for backup, recovery, or backup and recovery.

## PARAMETERS

### -Policy
Specifies the policy from which the schedule for backup is obtained.

```yaml
Type: CBPolicy
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

## INPUTS

### None

## OUTPUTS

### Microsoft.Internal.CloudBackup.Commands.OBSchedule

## NOTES

## RELATED LINKS

[Get-OBPolicy](./Get-OBPolicy.md)

[Set-OBSchedule](./Set-OBSchedule.md)

