---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: DfsrPowerShell.dll-Help.xml
Module Name: DFSR
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dfsr/get-dfsrbacklog?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-DfsrBacklog
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
The **Get-DfrsBacklog** cmdlet retrieves pending updates between two computers that participate in Distributed File System (DFS) Replication.

Updates can be new, modified, or deleted files and folders.
The maximum number of files that this command displays is 100.
The **Verbose** parameter displays a count of all backlogged updates.
Any files or folders listed in the DFS Replication backlog have not yet replicated from the source computer to the destination computer.
This is not necessarily an indication of problems.
A backlog indicates latency, and a backlog may be expected in your environment, depending on configuration, rate of change, network, and other factors.

## EXAMPLES

### Example 1: Retrieve unreplicated changes
```powershell
PS C:\> Get-DfsrBacklog -DestinationComputerName "SRV01" -SourceComputerName "SRV02" -GroupName "RG01" -FolderName "RF1A"
```
```output
Identifier                  : {DCE7FC28-5584-4D5D-BC84-2BD9D53CC2FC}-v538
Flags                       : 5
Attributes                  : 32
GlobalVersionSequenceNumber : {DCE7FC28-5584-4D5D-BC84-2BD9D53CC2FC}-v538
UpdateSequenceNumber        : 71576496
ParentId                    : {997D8F76-1207-49D7-85C9-DED015105A2F}-v1
FileId                      : 562949953495210
Volume                      : \\.\C:
Fence                       : 3
Clock                       : 130078672846368199
CreateTime                  : 3/15/2013 5:28:04 PM
UpdateTime                  : 3/15/2013 5:28:04 PM
FileHash                    : 173b51c11257a2eb 8c05884560fcfd1d
FileName                    : diskraid.exe
FullPathName                : c:\rf1a\diskraid.exe
Index                       : 1
ReplicatedFolderId          : 997d8f76-1207-49d7-85c9-ded015105a2f

Identifier                  : {DCE7FC28-5584-4D5D-BC84-2BD9D53CC2FC}-v539
Flags                       : 5
Attributes                  : 32
GlobalVersionSequenceNumber : {DCE7FC28-5584-4D5D-BC84-2BD9D53CC2FC}-v539
UpdateSequenceNumber        : 71577024
ParentId                    : {997D8F76-1207-49D7-85C9-DED015105A2F}-v1
FileId                      : 562949953495211
Volume                      : \\.\C:
Fence                       : 3
Clock                       : 130078672846524997
CreateTime                  : 3/15/2013 5:28:04 PM
UpdateTime                  : 3/15/2013 5:28:04 PM
FileHash                    : 6bcd377edf35e621 a7927703c08545d8
FileName                    : diskshadow.exe
FullPathName                : c:\rf1a\diskshadow.exe
Index                       : 2
ReplicatedFolderId          : 997d8f76-1207-49d7-85c9-ded015105a2f
```

This command retrieves the first 100 unreplicated changes between the local computer and the upstream computer SRV02 for the replication group RG01 and the replicated folder RF1A.
The command displays all file metadata.

### Example 2: Retrieve unreplicated changes between upstream and downstream computers
```powershell
PS C:\> Get-DfsrBacklog -DestinationComputerName "SRV01" -SourceComputerName "SRV02" -GroupName "RG01" -FolderName "RF1" | Format-Table FullPathName, UpdateTime
```
```output
FullPathName                      UpdateTime
------------                      ----------
c:\rf1a\imageres.dll       3/15/2013 5:28:45 PM
c:\rf1a\mshtml.dll         3/15/2013 5:28:50 PM
```

This command retrieves the first 100 unreplicated changes between the downstream computer SRV01 and the upstream computer SRV02 for the replication group RG01 and the replicated folder RF1.
The command also formats the output into a table that contains only the file paths and modification dates on the upstream server.

### Example 3: Retrieve unreplicated changes count to display
```powershell
PS C:\> Get-DfsrBacklog -GroupName "RG01" -FolderName "RF01" -SourceComputerName "SRV01" -DestinationComputerName "SRV02" -Verbose
```
```output
The replicated folder has a backlog of files. Replicated folder: "RF01". Count: 2400
```

This command retrieves the total count of unreplicated changes between the downstream computer SRV02 and the upstream computer SRV01 for the replication group RG01 and the replicated folder RF01.
The command displays this output in the verbose stream.

### Example 4: Retrieve unreplicated changes count to a string object
```powershell
PS C:\> (Get-DfsrBacklog -GroupName "RG01" -FolderName "RF01" -SourceComputerName "SRV01" -DestinationComputerName "SRV02" -Verbose 4>&1).Message.Split(':')[2]
```
```output
2400
```

This command retrieves the total count of unreplicated changes between the downstream computer SRV02 and the upstream computer SRV01 for the replication group RG01 and the replicated folder RF01.
The command converts the verbose stream data into a text string containing only the count, for later manipulation.

### Example 5: Retrieve unreplicated changes count to a file
```powershell
PS C:\> Get-DfsrBacklog -GroupName "RG01" -FolderName "RF01" -SourceComputerName "SRV01" -DestinationComputerName "SRV02" -Verbose 4> verbose.txt > null
PS C:\> Get-Content .\verbose.txt
```
```output
The replicated folder has a backlog of files. Replicated folder: "RF01". Count: 2400
```

This command retrieves the total count of unreplicated changes between the downstream computer SRV02 and the upstream computer SRV01 for the replication group RG01 and the replicated folder RF01.
The command converts the verbose stream data into a text string containing only the count, for later manipulation.

## PARAMETERS

### -DestinationComputerName
Specifies the name of the receiving computer.
A destination computer is also called an inbound or downstream computer.

```yaml
Type: String
Parameter Sets: (All)
Aliases: ReceivingMember, RMem

Required: True
Position: 3
Default value: None
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
Accept wildcard characters: True
```

### -GroupName
Specifies an array of names of replication groups.
If you do not specify this parameter, the cmdlet queries for all participating replications groups.
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
This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.DistributedFileSystemReplication.DfsReplicationGroup, Microsoft.DistributedFileSystemReplication.DfsReplicatedFolder, String computerName

## OUTPUTS

### Microsoft.DistributedFileSystemReplication.DfsrIdRecord

## NOTES

## RELATED LINKS

