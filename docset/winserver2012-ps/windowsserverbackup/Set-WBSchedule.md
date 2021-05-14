---
external help file: WSBackup_Cmdlets.xml
Module Name: WindowsServerBackup
online version: https://docs.microsoft.com/powershell/module/windowsserverbackup/set-wbschedule?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-WBSchedule

## SYNOPSIS
Sets the current schedule for backups.

## SYNTAX

```
Set-WBSchedule [-Policy] <WBPolicy> [-Schedule] <DateTime[]>
```

## DESCRIPTION
The **Set-WBSchedule** cmdlet sets the current schedule for backups and saves the settings in the **WBPolicy** object.

The **WBPolicy** object must be in edit mode.
To put the **WBPolicy** object in edit mode, use the Get-WBPolicy cmdlet with the **Editable** parameter.
The New-WBPolicy cmdlet creates a **WBPolicy** object that is already in edit mode.

To use this or any other Windows Server 2012 Backup cmdlets, you must be a member of the Administrators group or Backup Operators group.

## EXAMPLES

### Example 1: Set a backup policy schedule
```
PS C:\>$Policy = Get-WBPolicy PS C:\> Set-WBSchedule -Policy $Policy -Schedule 12:00,09:00
```

This command sets the scheduled times to create backups and saves the information in the **WBPolicy** object.
When you set this policy on the computer, backups are created daily at the specified times.

The first command stores the result of the Get-WBPolicy in the variable named **$Policy**.

The second command sets the backup schedule in the **$Policy** variable.
The **Schedule** parameter indicates the times.

## PARAMETERS

### -Policy
Specifies the **WBPolicy** object to update.

```yaml
Type: WBPolicy
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Schedule
Specifies the times of day to create a backup.
Time values are formatted as HH:MM and separated by a comma.

```yaml
Type: DateTime[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

## INPUTS

### WBPolicy,Datetime []
The Set-WBSchedule cmdlet references a **Datetime** object for the scheduled times and the **WBPolicy** object for the backup policy to update.

## OUTPUTS

### DateTime[]
The Set-WBSchedule cmdlet returns the **Datetime** list that you use to update the policy.

## NOTES

## RELATED LINKS

[Get-WBPolicy](./Get-WBPolicy.md)

[Get-WBSchedule](./Get-WBSchedule.md)

