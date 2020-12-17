---
external help file: DfsrPowerShell.dll-Help.xml
Module Name: DFSR
online version: 
schema: 2.0.0
title: Get-DfsrBacklog
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
ms.assetid: 933DF783-4CB6-4E94-87E4-D7E4EB1D3E59
---

# Get-DfsrBacklog

## SYNOPSIS
Retrieves the list of pending file updates between two DFS Replication partners.

## SYNTAX

```
Get-DfsrBacklog [[-GroupName] <String[]>] [[-FolderName] <String[]>] [-SourceComputerName] <String>
 [-DestinationComputerName] <String> [<CommonParameters>]
```

## DESCRIPTION
The **Get-DfrsBacklog** cmdlet retrieves pending updates between two computers that participate in DFS Replication.

Updates can be new, modified, or deleted files and folders.
The maximum number of files that this command displays is 100.
The **Verbose** parameter displays a count of all backlogged updates.
Any files or folders listed in the DFS Replication backlog have not yet replicated from the source computer to the destination computer.
This is not necessarily an indication of problems.
A backlog indicates latency, and a backlog may be expected in your environment, depending on configuration, rate of change, network, and other factors.

## EXAMPLES

### Example 12: Retrieve unreplicated changes between upstream and downstream computers1
```
PS C:\> Get-DfsrBacklog -DestinationComputerName SRV1 -SourceComputerName SRV02 -GroupName RG01 -FolderName RF1 | format-table fullpathname,updatetime


FullPathName                      UpdateTime
------------                      ----------
c:\rf1a\imageres.dll       3/15/2013 5:28:45 PM
c:\rf1a\mshtml.dll         3/15/2013 5:28:50 PM
```

This command retrieves the first 100 unreplicated changes between the downstream computer SRV1 and the upstream computer SRV02 for the replication group RG01 and the replicated folder RF1.
The command also formats the output into a table that contains only the file paths and modification dates on the upstream server.

### Example 23: Retrieve unreplicated changes count to display2
```
PS C:\>Get-DfsrBacklog -GroupName "RG01" -FolderName "RF01" -SourceComputerName "SRV01" -DestinationComputerName "SRV02" -Verbose
The replicated folder has a backlog of files. Replicated folder: "RF01". Count: 2400
```

This command retrieves the total count of unreplicated changes between the downstream computer SRV02 and the upstream computer SRV01 for the replication group RG01 and the replicated folder RF01.
The command displays this output in the verbose stream.

### Example 34: Retrieve unreplicated changes count to a string object3
```
PS C:\>(Get-DfsrBacklog -GroupName "RG01" -FolderName "RF01" -SourceComputerName "SRV01" -DestinationComputerName "SRV02" -Verbose 4>&1).Message.Split(':')[2]
2400
```

This command retrieves the total count of unreplicated changes between the downstream computer SRV02 and the upstream computer SRV01 for the replication group RG01 and the replicated folder RF01.
The command converts the verbose stream data into a text string containing only the count, for later manipulation.

### Example 45: Retrieve unreplicated changes count to a file4
```
PS C:\>Get-DfsrBacklog -GroupName "RG01" -FolderName "RF01" -SourceComputerName "SRV01" -DestinationComputerName "SRV02" -Verbose 4> verbose.txt > nullPS C:\> Get-Content .\verbose.txt
The replicated folder has a backlog of files. Replicated folder: "RF01". Count: 2400
```

This command retrieves the total count of unreplicated changes between the downstream computer SRV02 and the upstream computer SRV01 for the replication group RG01 and the replicated folder RF01.
The command converts the verbose stream data into a text string containing only the count, for later manipulation.

## PARAMETERS

### -DestinationComputerName
Specifies the name of the receiving computer.
A destination computer is also called an inbound or downstream computer.
If you do not specify this parameter, the cmdlet uses the local computer.

```yaml
Type: String
Parameter Sets: (All)
Aliases: ReceivingMember, RMem

Required: True
Position: 3
Default value: [local computer]
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -FolderName
Specifies an array of names of replicated folders.
If you do not specify this parameter, the cmdlet queries for all participating replicated folders.
You can specify multiple folders, separated by commas, as well as wildcard characters (*).

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: RF, RfName

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -GroupName
Specifies an array of names of replication groups.
If you do not specify this parameter, the cmdlet queries for all participating replications groups.
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

### -SourceComputerName
Specifies the name of the sending computer.
A source computer is also called an outbound or upstream computer.

```yaml
Type: String
Parameter Sets: (All)
Aliases: SendingMember, SMem

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.DistributedFileSystemReplication.DfsReplicationGroup, Microsoft.DistributedFileSystemReplication.DfsReplicatedFolder, string computerName

## OUTPUTS

### Microsoft.DistributedFileSystemReplication.DfsrIdRecord

## NOTES

## RELATED LINKS

