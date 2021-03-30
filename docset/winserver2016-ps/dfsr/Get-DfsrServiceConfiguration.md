---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-kaunu
author: Kateyanne
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: DfsrPowerShell.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: 
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-DfsrServiceConfiguration
ms.reviewer:
ms.assetid: B26D0DE7-0761-4AEB-B1AC-83DACF936CD5
---

# Get-DfsrServiceConfiguration

## SYNOPSIS
Gets settings for the DFS Replication service on group members.

## SYNTAX

```
Get-DfsrServiceConfiguration [[-ComputerName] <String[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-DfsrServiceConfiguration** cmdlet gets settings for the Distributed File System (DFS) Replication service on replication group members.
Members of a replication group host replicated folders.
Use this cmdlet to view settings for cleanup, debug logging, and automatic recovery for unexpected shut down.

## EXAMPLES

### Example 1: Get DFS Replication service settings for the local computer
```
PS C:\> Get-DfsrServiceConfiguration
ComputerName                      : SRV01
RPCPort                           : 
DynamicRPCPort                    : True
DisableDebugLog                   : False
MaximumDebugLogFiles              : 1000
DebugLogPath                      : C:\Windows\debug
DebugLogSeverity                  : 4
MaximumDebugLogMessages           : 200000
UnexpectedAutoRecovery            : False
CleanupStagingFolderAtPercent     : 90
CleanupStagingFolderUntilPercent  : 60
CleanupConflictFolderAtPercent    : 90
CleanupConflictFolderUntilPercent : 60
```

This command gets the DFS Replication service settings for the local computer.

## PARAMETERS

### -ComputerName
Specifies an array of names of replication member computers.
You can use a comma separated list and the wildcard character (*).
If you do not specify this parameter, the cmdlet uses the current computer.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: MemberList, MemList

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### String

## OUTPUTS

### Microsoft.DistributedFileSystemReplication.DfsrServiceConfiguration

## NOTES

## RELATED LINKS

[Set-DfsrServiceConfiguration](./Set-DfsrServiceConfiguration.md)

