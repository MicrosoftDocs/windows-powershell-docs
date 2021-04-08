---
author: Kateyanne
description: 
external help file: DfsrPowerShell.dll-Help.xml
manager: jasgro
Module Name: DFSR
ms.author: v-kaunu
ms.date: 10/30/2017
ms.prod: powershell
ms.reviewer: brianlic
ms.topic: reference
online version: https://docs.microsoft.com/powershell/module/dfsr/get-dfsrstate?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-DfsrState
---

# Get-DfsrState

## SYNOPSIS
Gets the DFS Replication state for a member.

## SYNTAX

```
Get-DfsrState [[-ComputerName] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-DfsrState** cmdlet gets the overall DFS Replication state for a computer in regard to its replication group partners.
The cmdlet returns both inbound and outbound file replication information, such as files currently replicating and files immediately queued to replicate next.

## EXAMPLES

### Example 1: Get the DFS Replication state for a member
```
PS C:\> Get-DfsrState -ComputerName "SRV02" | Format-Table FileName,UpdateState,Inbound,Source* -Auto -Wrap


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

This command gets the list of files currently replicating or queued inbound and outbound from the computer named SRV02.

## PARAMETERS

### -ComputerName
Specifies the name of a replication member computer.
If you do not specify this parameter, the cmdlet uses the current computer.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Member, Mem

Required: False
Position: 0
Default value: [local computer]
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### string

## OUTPUTS

### microsoft.distributedfilesystemreplication.dfsrupdate

## NOTES

## RELATED LINKS

[Get-DfsReplicationGroup](./Get-DfsReplicationGroup.md)

