---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-anbarr
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: DfsrPowerShell.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-DfsrConnectionSchedule
ms.reviewer:
ms.assetid: BF13E026-9450-4B10-8A69-0CB198623BE3
---

# Get-DfsrConnectionSchedule

## SYNOPSIS
Gets a connection schedule between members of a replication group.

## SYNTAX

```
Get-DfsrConnectionSchedule [[-GroupName] <String[]>] [-SourceComputerName] <String>
 [-DestinationComputerName] <String> [[-DomainName] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-DfsrConnectionSchedule** cmdlet gets a connection schedule.

Distributed File System (DFS) Replication connections are the logical partnerships between members in a replication group.
The DFS Replication service uses the Remote Procedure Call (RPC) protocol to communicate between servers.
DFS Replication schedules control the availability and bandwidth usage of replication.

## EXAMPLES

### Example 1: Get a connection schedule
```
PS C:\> Get-DfsrConnectionSchedule -GroupName "RG24" -SourceComputerName "SRV02" -DestinationComputerName "SRV01"


GroupName               : RG24
SourceComputerName      : SRV02
DestinationComputerName : SRV1
DomainName              : corp.contoso.com
ConnectionGuid          : b3249896-e3ec-468b-a06a-31946d86e426
UseUTC                  : False
HoursReplicated         : 168
BandwidthDetail         : Using the replication group's schedule
```

This command gets the connection-based replication schedule from the server named SRV02 to the server named SRV01.
Because the administrator has not specified a custom schedule for the connection, the connection inherits the schedule settings from the replication group.

### Example 2: Get a custom connection schedule
```
PS C:\> Get-DfsrConnectionSchedule -GroupName "RG24" -SourceComputerName "SRV01" -DestinationComputerName "SRV02"


GroupName               : RG24
SourceComputerName      : SRV01
DestinationComputerName : SRV22
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

This command gets the connection-based replication schedule from the server named SRV01 to the server named SRV02.
The cmdlet gets a custom connection schedule that blocks replication from 9 A.M.
to 5 P.M.
Monday through Friday (represented by zeros in the output), and allows full bandwidth replication for all remaining time blocks.

## PARAMETERS

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
Accept wildcard characters: False
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
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.DistributedFileSystemReplication.DfsReplicationGroup

## OUTPUTS

### Microsoft.DistributedFileSystemReplication.DfsrConnectionSchedule, string

## NOTES

## RELATED LINKS

[Set-DfsrConnectionSchedule](./Set-DfsrConnectionSchedule.md)

