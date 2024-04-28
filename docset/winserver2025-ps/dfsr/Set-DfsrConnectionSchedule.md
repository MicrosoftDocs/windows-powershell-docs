---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: DfsrPowerShell.dll-Help.xml
Module Name: DFSR
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dfsr/set-dfsrconnectionschedule?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-DfsrConnectionSchedule
---

# Set-DfsrConnectionSchedule

## SYNOPSIS
Changes the settings of a connection schedule between members of a replication group.

## SYNTAX

### ScheduleNameParameterSet (Default)
```
Set-DfsrConnectionSchedule [[-GroupName] <String[]>] [-SourceComputerName] <String>
 [-DestinationComputerName] <String> [[-UseUTC] <Boolean>] [[-ScheduleType] <ConnectionScheduleType>]
 [[-DomainName] <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### CustomScheduleParameterSet
```
Set-DfsrConnectionSchedule [[-GroupName] <String[]>] [-SourceComputerName] <String>
 [-DestinationComputerName] <String> [[-UseUTC] <Boolean>] [-Day] <DayOfWeek[]> [-BandwidthDetail] <String>
 [[-DomainName] <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-DfsrConnectionSchedule** cmdlet changes the schedule and bandwidth throttle of a connection between two members of a replication group.

Distributed File System (DFS) Replication connections are the logical partnerships between members in a replication group.
The DFS Replication service uses the Remote Procedure Call (RPC) protocol to communicate between servers.
By default, DFS Replication creates connections with the recommended schedule and bandwidth configuration: full bandwidth, and 24 hours per day, seven days per week availability.

## EXAMPLES

### Example 1: Configure a full connection schedule
```
PS C:\> Set-DfsrConnectionSchedule -GroupName "RG24" -SourceComputerName "SRV01" -DestinationComputerName "SRV02" -ScheduleType Always
GroupName               : RG24
SourceComputerName      : SRV01
DestinationComputerName : SRV02
DomainName              : corp.contoso.com
ConnectionGuid          : fb4a502f-48d1-4926-ae29-c1e90b32c139
UseUTC                  : False
HoursReplicated         : 168
BandwidthDetail         : FFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF
FFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF
FFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF
FFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF
FFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF
FFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF
FFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF
FFFFFFFFFFFFFFFFFFFFF
```

This command configures the connection schedule from the server named SRV01 to the server named SRV02 in the RG24 replication group.
The *ScheduleType* parameter specifies a full schedule that enables replication 24 hours a day, seven days a week that uses full bandwidth.

### Example 2: Set a connection schedule
```
PS C:\> Set-DfsrConnectionSchedule -GroupName "RG24" -SourceComputerName "SRV01" -DestinationComputerName "SRV01" -Day Monday,Tuesday,Wednesday,Thursday,Friday - BandwidthDetail "ffffffffffffffffffffffffffffffffffff00000000000000000000000000000000ffffffffffffffffffffffffffff"


GroupName               : RG 1
SourceComputerName      : SRV1
DestinationComputerName : SRV2
DomainName              : corp.contoso.com
ConnectionGuid          : fb4a502f-48d1-4926-ae29-c1e90b32c139
UseUTC                  : False
HoursReplicated         : 128
BandwidthDetail         : FFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF
FFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF00000000000000000000000000000000FFFFFFFFFFFFFFFFFFFFFF
FFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF00000000000000000000000000000000FFFFFFFFFFFFFFFFFFF
FFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF00000000000000000000000000000000FFFFFFFFFFFFFFFF
FFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF00000000000000000000000000000000FFFFFFFFFFFFF
FFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF00000000000000000000000000000000FFFFFFFFFF
FFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF
FFFFFFFFFFFFFFFFFFFFF
```

This command configures the connection schedule from the server named SRV01 to the server named SRV02 in the RG24 replication group.
The command specifies that the DFS Replication service prevents all replication from 9 A.M.
to 5 P.M.
Monday through Friday, and allows replicating in all other intervals at full bandwidth.

## PARAMETERS

### -BandwidthDetail
Specifies a custom schedule value string.

The schedule value defines the settings for each 15-minute interval block with its bandwidth, with 4 blocks to a set, where each set represents 1 hour.
There are 24 sets.
The time starts at 00:00 and ends at 24:00.
The valid settings on a 15-minute block are 0 (zero) through F, using hexadecimal.
The following shows the mapping of the valid settings:

0 = No replication
1 = 16 kilobits per second (Kbps)
2 = 64 Kbps
3 = 128 Kbps
4 = 256 Kbps
5 = 512 Kbps
6 = 1 megabit per second (Mbps)
7 = 2 Mbps
8 = 4 Mbps
9 = 8 Mbps
A = 16 Mbps
B = 32 Mbps
C = 64 Mbps
D = 128 Mbps
E = 256 Mbps
F = Full bandwidth replication

A complete value string must include all 24 sets with 4 blocks to a set, for a total of 96 hexadecimal characters.
For example: ffffffffffff0000ffff0000ffff00004444000044440000444400004444000044440000ffff0000ffff0000ffffffff

```yaml
Type: String
Parameter Sets: CustomScheduleParameterSet
Aliases:

Required: True
Position: 5
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
Specifies an array of days of the week.
You can specify either an enumerated string value or its corresponding integer for this parameter.
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
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DestinationComputerName
Specifies the name of the receiving computer.
A receiving computer is also called an inbound or downstream computer.

```yaml
Type: String
Parameter Sets: (All)
Aliases: ReceivingMember, RMem

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -DomainName
Specifies the NetBIOS name or fully qualified domain name (FQDN) for the Active Directory Domain Service (AD DS) domain that contains the replication group.
If you do not specify this parameter, the cmdlet uses the domain of the current user.

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
You can use a comma separated list and the wildcard character (*).

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: RG, RgName

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### -ScheduleType
Specifies the type of connection schedule.
You can specify the inherited replication group schedule, a connection-based closed schedule that allows no replication, or a connection-based full schedule that enables replication for 24 hours a day, seven days a week using full bandwidth.
You can specify either an enumerated string value or its corresponding integer for this parameter.
The acceptable values for this parameter are:

- UseGroupSchedule (0)
- Never (1)
- Always (2)

```yaml
Type: ConnectionScheduleType
Parameter Sets: ScheduleNameParameterSet
Aliases:
Accepted values: UseGroupSchedule, Never, Always

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SourceComputerName
Specifies the name of the sending computer.
A sending computer is also called an outbound or upstream computer.

```yaml
Type: String
Parameter Sets: (All)
Aliases: SendingMember, SMem

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -UseUTC
Indicates whether the destination computer uses Coordinated Universal Time (UTC) for the schedule.
By default, the destination computer interprets the schedule in its own local time.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
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

### Microsoft.DistributedFileSystemReplication.DfsReplicationGroup, String

## OUTPUTS

### Microsoft.DistributedFileSystemReplication.DfsrConnectionSchedule

## NOTES

## RELATED LINKS

[Get-DfsrConnectionSchedule](./Get-DfsrConnectionSchedule.md)

