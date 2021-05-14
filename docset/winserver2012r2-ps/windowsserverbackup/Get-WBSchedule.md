---
external help file: wsbcmdlet.dll-Help.xml
Module Name: WindowsServerBackup
ms.date: 10/30/2017
online version: https://docs.microsoft.com/powershell/module/windowsserverbackup/get-wbschedule?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WBSchedule
---

# Get-WBSchedule

## SYNOPSIS
Retrieves the current schedule for backups.

## SYNTAX

```
Get-WBSchedule [-Policy] <WBPolicy> [<CommonParameters>]
```

## DESCRIPTION
The **Get-WBSchedule** cmdlet retrieves the current schedule for backups in the **WBPolicy** object.
Backups run daily at the times specified in the schedule.
To change the schedule, use the **Set-WBSchedule** cmdlet.

To use this cmdlet, you must be a member of the Administrators group or Backup Operators group.

## EXAMPLES

### Example 1: Get the scheduled backup times
```
PS C:\> $Policy = Get-WBPolicy
PS C:\> Get-WBSchedule -Policy $Policy
```

This example gets the scheduled backup times from the **WBPolicy** object.

The first command stores the result of the Get-WBPolicy in the variable named **$Policy**.

The second command gets the backup schedule from the backup policy object.

## PARAMETERS

### -Policy
Specifies the **WBPolicy** object to display.

```yaml
Type: WBPolicy
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

### WBPolicy
The Get-WBSchedule cmdlet queries a specified **WBPolicy** object.

## OUTPUTS

### Datetime []
The Get-WBSchedule cmdlet displays the list of **Datetime** objects in the **WBPolicy** object.

## NOTES

## RELATED LINKS

[New-WBPolicy](./New-WBPolicy.md)

[Set-WBSchedule](./Set-WBSchedule.md)

