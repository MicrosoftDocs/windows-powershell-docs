---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: DfsrPowerShell.dll-Help.xml
Module Name: DFSR
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dfsr/get-dfsrgroupschedule?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-DfsrGroupSchedule
---

# Get-DfsrGroupSchedule

## SYNOPSIS
Retrieves a replication group schedule.

## SYNTAX

```
Get-DfsrGroupSchedule [[-GroupName] <String[]>] [[-DomainName] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-DfsrGroupSchedule** cmdlet retrieves a schedule from a specified replication group.
Distributed File System (DFS) Replication schedules control the availability and bandwidth usage of replication.
By default, DFS Replication schedules replication 24 hours a day, 7 days a week with full bandwidth as the recommended configuration.

The DFS Replication Get-* cmdlets are useful for pipeline operations or inventory.

## EXAMPLES

### Example 1: Get a group schedule
```
PS C:\> Get-DfsrGroupSchedule -GroupName "RG01"
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

This command uses the **Get-DfsrGroupSchedule** cmdlet to display the replication group schedule for a resource group named RG01.

## PARAMETERS

### -DomainName
Specifies the NetBIOS name or fully qualified domain name (FQDN) for the Active Directory Domain Service (AD DS) domain that contains a replication group.
If you do not specify this parameter, the cmdlet uses the current domain of the user.

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
If you do not specify this parameter, the cmdlet queries for all participating replication groups.
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.DistributedFileSystemReplication.DfsReplicationGroup

## OUTPUTS

### Microsoft.DistributedFileSystemReplication.DfsRGroupSchedule

## NOTES

## RELATED LINKS

[Set-DfsrGroupSchedule](./Set-DfsrGroupSchedule.md)

