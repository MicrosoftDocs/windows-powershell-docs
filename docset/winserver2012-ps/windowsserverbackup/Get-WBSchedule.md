---
external help file: WSBackup_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: 0C09CB71-DADA-4DF6-AF95-F7E6D5045AAA
manager: dansimp
---

# Get-WBSchedule

## SYNOPSIS
Retrieves the current schedule for backups.

## SYNTAX

```
Get-WBSchedule [-Policy] <WBPolicy>
```

## DESCRIPTION
The **Get-WBSchedule** cmdlet retrieves the current schedule for backups in the **WBPolicy** object.
Backups run daily at the times specified in the schedule.
To change the schedule, use the **Set-WBSchedule** cmdlet.

To use this or any other Windows Server 2012 Backup cmdlets, you must be a member of the Administrators group or Backup Operators group.

## EXAMPLES

### Example 1: Get the scheduled backup times
```
PS C:\>$Policy = Get-WBPolicy PS C:\> Get-WBSchedule -Policy $Policy
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
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

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

