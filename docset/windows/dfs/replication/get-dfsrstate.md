---
author: brianlic-msft
description: 
external help file: DfsrPowerShell.dll-Help.xml
keywords: powershell, cmdlet
manager: alanth
ms.date: 2016-12-20
ms.prod: powershell
ms.technology: powershell
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-DfsrState
ms.assetid: CD5B9830-CF5B-415B-A3B4-57A30D1C0310
---

# Get-DfsrState

## SYNOPSIS
Gets the DFS Replication state for a member.

## SYNTAX

```
Get-DfsrState [[-ComputerName] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-DfsrState** cmdlet gets the overall Distributed File System (DFS) Replication state for a computer in regard to its replication group partners.
The cmdlet returns both inbound and outbound file replication information, such as files currently replicating and files immediately queued to replicate next.

## EXAMPLES

### Example 1: Get the DFS Replication state for a member
```
PS C:\> Get-DfsrState -ComputerName "SRV01" | Format-Table filename,updatestate,inbound,source* -auto -wrap


FileName                   UpdateState Inbound SourceComputerName
--------                   ----------- ------- ------------------
ntfrs - Copy.exe             Scheduled    True SRV02
ntdsai - Copy.dll            Scheduled    True SRV02
NlsLexicons0046 - Copy.dll   Scheduled    True SRV02
NlsLexicons000a - Copy.dll Downloading    True SRV02
occache - Copy.dll           Scheduled    True SRV02
NlsModels0011 - Copy.dll     Scheduled    True SRV02
NlsLexicons0007 - Copy.dll   Scheduled    True SRV02
NlsLexicons000f - Copy.dll Downloading    True SRV02
NlsLexicons003e - Copy.dll   Scheduled    True SRV02
NlsLexicons0045 - Copy.dll   Scheduled    True SRV02
NlsData001a - Copy.dll     Downloading    True SRV02
ntlanui2 - Copy.dll          Scheduled    True SRV02
```

This command gets the list of files currently replicating or queued inbound and outbound from the computer named SRV01.

## PARAMETERS

### -ComputerName
Specifies an array of names of computers.
The cmdlet adds these computers to the replication group specified by the **GroupName** parameter.
You can use a comma separated list and the wildcard character (*).

```yaml
Type: String
Parameter Sets: (All)
Aliases: Member, Mem

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### String

## OUTPUTS

### Microsoft.DistributedFileSystemReplication.DfsrUpdate

## NOTES

## RELATED LINKS

[Get-DfsReplicationGroup](./Get-DfsReplicationGroup.md)

