---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: DfsrPowerShell.dll-Help.xml
Module Name: DFSR
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dfsr/set-dfsrgroupschedule?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-DfsrGroupSchedule
---

# Set-DfsrGroupSchedule

## SYNOPSIS
Modifies a replication group schedule.

## SYNTAX

### ScheduleNameParameterSet (Default)
```
Set-DfsrGroupSchedule [-GroupName] <String[]> [[-UseUTC] <Boolean>] [[-ScheduleType] <GroupScheduleType>]
 [[-DomainName] <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### CustomScheduleParameterSet
```
Set-DfsrGroupSchedule [-GroupName] <String[]> [[-UseUTC] <Boolean>] [-Day] <DayOfWeek[]>
 [-BandwidthDetail] <String> [[-DomainName] <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-DfsrGroupSchedule** cmdlet modifies a schedule for a replication group.
Distributed File System (DFS) Replication schedules control the availability and bandwidth usage of replication.

By default, DFS Replication schedules replication 24 hours per day, 7 days per week with full bandwidth as the recommended configuration.

## EXAMPLES

### Example 1: Modify a group schedule
```
PS C:\> Set-DfsrGroupSchedule -GroupName "RG01" -ScheduleType Always
GroupName            : RG01
DomainName           : corp.contoso.com
ReplicationGroupGuid : 1f06f8d4-a0ae-4221-99d2-0bd1bb27882b
UseUTC               : False
HoursReplicated      : 168
BandwidthDetail      : FFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF
FFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF
FFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF
FFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF
FFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF
FFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF
FFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF
```

This command uses the **Set-DfsrGroupSchedule** cmdlet to modify the RG01 replication group to allow full replication 24 hours per day, 7 days per week.
The command also uses the *ScheduleType* parameter so there is no need to specify any specific bandwidth blocks or days.

### Example 2: Modify a group schedule to prevent replication
```
PS C:\> Set-DfsrGroupSchedule -GroupName "RG01" -Day Monday,Tuesday,Wednesday,Thursday,Friday -BandwidthDetail ffffffffffffffffffffffffffffffffffff00000000000000000000000000000000ffffffffffffffffffffffffffff
GroupName            : RG01
DomainName           : corp.contoso.com
ReplicationGroupGuid : 1f06f8d4-a0ae-4221-99d2-0bd1bb27882b
UseUTC               : False
HoursReplicated      : 128
BandwidthDetail      : FFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF
FFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF00000000000000000000000000000000FFFFFFFFFFFFFFFFFFFFFFFFFFFF
FFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF00000000000000000000000000000000FFFFFFFFFFFFFFFFFFFFFFFFFFFF
FFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF00000000000000000000000000000000FFFFFFFFFFFFFFFFFFFFFFFFFFFF
FFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF00000000000000000000000000000000FFFFFFFFFFFFFFFFFFFFFFFFFFFF
FFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF00000000000000000000000000000000FFFFFFFFFFFFFFFFFFFFFFFFFFFF
FFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF
```

This command uses the **Set-DfsrGroupSchedule** cmdlet to modify the RG01 replication group schedule to prevent all replication from 9AM to 5PM Monday through Friday, with all other intervals replicating at full bandwidth.

## PARAMETERS

### -BandwidthDetail
Specifies a custom schedule value string that defines the bandwidth settings for each 15-minute interval block, with 4 blocks to a set, where each set represents 1 hour, and there are 24 sets.
The time starts at 00:00 and ends at 24:00.
The valid settings on a 15-minute block are 0 through F, with the following mapping of settings:

- 0 = No replication
- 1 = 16 kilobits per second (Kbps)
- 2 = 64 Kbps
- 3 = 128 Kbps
- 4 = 256 Kbps
- 5 = 512 Kbps
- 6 = 1 megabit per second (Mbps)
- 7 = 2 Mbps
- 8 = 4 Mbps
- 9 = 8 Mbps
- A = 16 Mbps
- B = 32 Mbps
- C = 64 Mbps
- D = 128 Mbps
- E = 256 Mbps
- F = Full bandwidth replication

You must specify a complete value string and include all 24 hourly 4-block sets (for a total of 96 hexadecimal characters).
For example: ffffffffffff0000ffff0000ffff00004444000044440000444400004444000044440000ffff0000ffff0000ffffffff

```yaml
Type: String
Parameter Sets: CustomScheduleParameterSet
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Day
Specifies a day of the week.
You can specify either an enumerated string value or its corresponding integer value.
The acceptable values for this parameter are:

- Sunday (0)
- Monday (1)
- Tuesday (2)
- Wednesday (3)
- Thursday (4)
- Friday (5)
- Saturday (6)

```yaml
Type: DayOfWeek[]
Parameter Sets: CustomScheduleParameterSet
Aliases:
Accepted values: Sunday, Monday, Tuesday, Wednesday, Thursday, Friday, Saturday

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DomainName
Specifies the NetBIOS name or fully qualified domain name (FQDN) for the Active Directory Domain Service (AD DS) domain that contains a replication group.
If you do not specify this parameter, the cmdlet uses the current domain.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 100
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -GroupName
Specifies an array of names of replication groups.
If you do not specify this parameter, the cmdlet applies to all participating replication groups.
You can use a comma separated list and the wildcard character (*).

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: RG, RgName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### -ScheduleType
Specifies a schedule type with no replication allowed or a full schedule that enables replication for 24 hours a day, 7 days a week using full bandwidth.
The acceptable values for this parameter are: Never (0) and Always (1).
You can specify either an enumerated string value or its corresponding integer value for this parameter.

```yaml
Type: GroupScheduleType
Parameter Sets: ScheduleNameParameterSet
Aliases:
Accepted values: Never, Always

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseUTC
Indicates whether the destination computer uses Coordinated Universal Time (UTC) for its schedule.
By default, the destination computer interprets the schedule according to its local time.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.DistributedFileSystemReplication.DfsReplicationGroup

## OUTPUTS

### Microsoft.DistributedFileSystemReplicationDfsrgroupSchedule

## NOTES

## RELATED LINKS

[Get-DfsrGroupSchedule](./Get-DfsrGroupSchedule.md)

