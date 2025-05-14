---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: DfsrPowerShell.dll-Help.xml
Module Name: DFSR
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dfsr/write-dfsrhealthreport?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Write-DfsrHealthReport
---

# Write-DfsrHealthReport

## SYNOPSIS
Generates a DFS Replication health report.

## SYNTAX

```
Write-DfsrHealthReport [-GroupName] <String[]> [[-ReferenceComputerName] <String>]
 [[-MemberComputerName] <String[]>] [[-Path] <String>] [-CountFiles] [[-DomainName] <String>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Write-DfsrHealthReport** cmdlet generates a Distributed File System (DFS) Replication health, or diagnostic, report for two or more servers.
A health reports contains administrative information about replication state, efficiency, and any potential replication issues.

The cmdlet creates the reports as an HTML file, with an associated XML file.

## EXAMPLES

### Example 1: Generate a health report with a file count
```
PS C:\> Write-DfsrHealthReport -GroupName "RG01" -ReferenceComputerName "SRV01" -MemberComputerName "SRV02" -Path "C:\reports" -CountFiles
```

This command generates a report for the replication group RG01 and the reference computer SRV01.

### Example 2: Generate a health report
```
PS C:\> Write-DfsrHealthReport -GroupName "RG01" -ReferenceComputerName "SRV01" -Verbose
VERBOSE: Performing operation "Write-DfsrHealthReport" on Target "RG01".
VERBOSE: Successfully saved the health report for the replication group named "RG01". The XML file is located here: "C:\Health-RG01-04Apr2013-2022.xml". The HTML file is located here: "C:\Health-RG01-04Apr2013-2022.html".
```

This command generates a health report for the RG01 replication group with a baseline computer of SRV01 and all other servers in the replication group.
The command writes the report to the C:\ folder.

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

### -CountFiles
Indicates that the cmdlet counts the number of files present in the replicated content folders.
By default, the cmdlet does not count files, in order to save time while generating a report.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### -MemberComputerName
Specifies an array of DFS Replication members to analyze in comparison to a server specified by the *ReferenceComputerName* parameter.
If you do not specify this parameter, the cmdlet includes all members of the replication group.
You can specify multiple computer names, separated by commas, as well as wildcard characters (*).

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: MemberList, MemList

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Path
Specifies the folder path for the report file.
If you do not specify this parameter, the cmdlet uses the current working directory.

The cmdlet names each report in the format Health-\<Replication Group Name\>-\<Date\>-\<Time\> with HTML and XML extensions.

```yaml
Type: String
Parameter Sets: (All)
Aliases: FilePath

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ReferenceComputerName
Specifies the name of a reference computer in the replication group.
The replication backlog from this server is compared to all other members specified in the *MemberComputerName* parameter.
If you do not specify this parameter, the cmdlet uses the local computer.

```yaml
Type: String
Parameter Sets: (All)
Aliases: ReferenceMember, RefMem

Required: False
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

### Microsoft.DistributedFileSystemReplication.DfsReplicationGroup

## OUTPUTS

### None

## NOTES

## RELATED LINKS

