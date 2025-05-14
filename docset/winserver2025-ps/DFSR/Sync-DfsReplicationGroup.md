---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: DfsrPowerShell.dll-Help.xml
Module Name: DFSR
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dfsr/sync-dfsreplicationgroup?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Sync-DfsReplicationGroup
---

# Sync-DfsReplicationGroup

## SYNOPSIS
Synchronizes replication between computers regardless of schedule.

## SYNTAX

```
Sync-DfsReplicationGroup [-GroupName] <String[]> [-SourceComputerName] <String>
 [-DestinationComputerName] <String> [-DurationInMinutes] <UInt32> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Sync-DfsReplicationGroup** cmdlet synchronizes replication between a source computer and a destination computer, even if replication is not scheduled by either a replication group or a connection.

This cmdlet ignores the schedule for the specified number of minutes.
Use this cmdlet to alter the schedule temporarily to allow replication, because this cmdlet does not require Active Directory replication and LDAP polling.

## EXAMPLES

### Example 1: Replicate between servers for 15 minutes
```
PS C:\> Sync-DfsReplicationGroup -GroupName "RG01" -SourceComputerName "SRV01" -DestinationComputerName "SRV02" -DurationInMinutes 15
```

This command allows replication from server SRV01 to SRV02 in the RG01 replication group for 15 minutes, even if the replication happens during a closed replication schedule.

### Example 2: Replicate between servers with verbose output
```
PS C:\> Sync-DfsReplicationGroup -GroupName "RG01" -SourceComputerName "SRV01" -DestinationComputerName "SRV02" -DurationInMinutes 5 -Verbose
VERBOSE: Performing operation "Sync-DfsReplicationGroup" on Target "SRV01".
VERBOSE: The **Sync-DfsReplicationGroup** cmdlet completed successfully.
```

This command allows replication from server SRV01 to SRV02 in the RG01 replication group for 5 minutes.

## PARAMETERS

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

### -DestinationComputerName
Specifies the name of the receiving computer.
A destination computer is also  called an inbound or downstream computer.
This computer overrides its schedule and replicates inbound.

```yaml
Type: String
Parameter Sets: (All)
Aliases: ReceivingMember, RMem

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DurationInMinutes
Specifies the number of minutes to allow replication.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: Time

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GroupName
Specifies an array of names of replication groups.
If you do not specify this parameter, the cmdlet queries for all participating replication groups.
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

### -SourceComputerName
Specifies the name of the sending computer.
A source computer is also called an outbound or upstream computer.

```yaml
Type: String
Parameter Sets: (All)
Aliases: SendingMember, SMem

Required: True
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

### Microsoft.DistributedFileSystemReplication.DfsReplicationGroup, uint, string Computername, string Computername

## OUTPUTS

### Microsoft.DistributedFileSystemReplication.DfsReplicationGroup

## NOTES

## RELATED LINKS

[Get-DfsReplicationGroup](./Get-DfsReplicationGroup.md)

[New-DfsReplicationGroup](./New-DfsReplicationGroup.md)

[Remove-DfsReplicationGroup](./Remove-DfsReplicationGroup.md)

[Set-DfsReplicationGroup](./Set-DfsReplicationGroup.md)

[Suspend-DfsReplicationGroup](./Suspend-DfsReplicationGroup.md)

