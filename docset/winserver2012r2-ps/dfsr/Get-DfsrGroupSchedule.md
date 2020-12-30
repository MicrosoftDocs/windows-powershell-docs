---
external help file: DfsrPowerShell.dll-Help.xml
Module Name: DFSR
online version: 
schema: 2.0.0
title: Get-DfsrGroupSchedule
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 417B52C3-55A2-4445-AED8-E9DD65E0EAAB
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
DFS Replication schedules control the availability and bandwidth usage of replication.
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

This command uses the Get-DfsrGroupSchedule cmdlet to display the replication group schedule for a resource group named RG01.

## PARAMETERS

### -DomainName
Specifies a NetBIOS or fully qualified domain name (FQDN) for an Active Directory domain containing the replication group.
If you do not specify this parameter, the cmdlet uses the current domain of the user.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 100
Default value: [Current Domain]
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -GroupName
Specifies  an array of names of replication groups.
If you do not specify this parameter, the cmdlet queries for all participating replication groups.
You can specify multiple groups, separated by commas, as well as wildcard characters (*).

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: RG, RgName

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.DistributedFileSystemReplication.DfsReplicationGroup

## OUTPUTS

### Microsoft.DistributedFileSystemReplication.DfsRGroupSchedule

## NOTES

## RELATED LINKS

[Set-DfsrGroupSchedule](./Set-DfsrGroupSchedule.md)

