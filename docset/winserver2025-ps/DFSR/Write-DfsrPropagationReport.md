---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: DfsrPowerShell.dll-Help.xml
Module Name: DFSR
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dfsr/write-dfsrpropagationreport?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Write-DfsrPropagationReport
---

# Write-DfsrPropagationReport

## SYNOPSIS
Generates reports for propagation test files in a replication group.

## SYNTAX

```
Write-DfsrPropagationReport [-GroupName] <String[]> [-FolderName] <String[]> [-ReferenceComputerName] <String>
 [[-Path] <String>] [[-FileCount] <Int32>] [[-DomainName] <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Write-DfsrPropagationReport** cmdlet generates reports for the replication progress of propagation test files in a replication group.
Specify the replication group, replicated folder, and a member computer to act as the reference computer.

The cmdlet creates files named Propagation-\<RG Name\>-\<Date\>-\<Time\>.html and Propagation-\<RG Name\>-\<Date\>-\<Time\>.xml.
You can specify a folder to save these files to, or use the current working directory.

Use the **Start-DfsrPropagationTest** cmdlet to create a propagation test file.

## EXAMPLES

### Example 1: Create a propagation report for a specific group and replicated folder
```
PS C:\> Write-DfsrPropagationReport -GroupName "RG01" -FolderName "RF22" -ReferenceComputerName "SRV01" -Path "C:\Reports"
```

This command creates a propagation report, as HTML and XML files, in the folder C:\Reports.
The command specifies SRV01 as reference computer and specifies group name and folder name.

### Example 2: Create propagation reports for all groups and replicated folders by using wildcards
```
PS C:\> Write-DfsrPropagationReport -GroupName * -FolderName * -ReferenceComputerName "SRV01" -Verbose
VERBOSE: Performing operation "Write-DfsrPropagationReport" on Target "DFSR membership with domain: corp.contoso.com;
replication group: RG 1; replicated folder: RF 1; computer: SRV01; GUID: {966e2e84-7792-438f-8344-c8f76d214d06}.".
VERBOSE: Successfully saved the propagation report for DFSR membership with domain: corp.contoso.com; replication
group: RG 1; replicated folder: RF 1; computer: SRV01; GUID: {966e2e84-7792-438f-8344-c8f76d214d06}. The XML file is
located here: "C:\Propagation-RG 1-RF 1-04Apr2013-2109.xml". The HTML file is located here: "C:\Propagation-RG 1-RF
1-04Apr2013-2109.html".
VERBOSE: Performing operation "Write-DfsrPropagationReport" on Target "DFSR membership with domain: corp.contoso.com;
replication group: Branch Office 1; replicated folder: Data Distribution 1; computer: SRV01; GUID:
{dbaa3a16-f731-4428-8a4f-8278673e848a}.".
VERBOSE: Successfully saved the propagation report for DFSR membership with domain: corp.contoso.com; replication
group: Branch Office 1; replicated folder: Data Distribution 1; computer: SRV01; GUID:
{dbaa3a16-f731-4428-8a4f-8278673e848a}. The XML file is located here: "C:\Propagation-Branch Office 1-Data Distribution
1-04Apr2013-2109.xml". The HTML file is located here: "C:\Propagation-Branch Office 1-Data Distribution
1-04Apr2013-2109.html".
```

This command creates propagation reports for all replicated folders in all replication groups by using a wildcard character (*) for the **GroupName** and **FolderName** parameters.
The command specifies SRV01 as the reference computer.
This command uses the *Verbose* parameter to display information to the console.

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

### -FileCount
Specifies the number of most recently generated propagation test files to use for generating the report.
If you do not specify this parameter, the cmdlet uses all files.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FolderName
Specifies an array of names of replicated folders.
If you do not specify this parameter, the cmdlet applies to all participating replicated folders.
You can use a comma separated list and the wildcard character (*).

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: RF, RfName

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -GroupName
Specifies an array of names of replication groups.
If you do not specify this parameter, the cmdlet applies to all participating replication groups.
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

### -Path
Specifies a folder for the report file.
If you do not specify this parameter, the cmdlet uses the current working directory.

```yaml
Type: String
Parameter Sets: (All)
Aliases: FilePath

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ReferenceComputerName
Specifies the name of a reference computer in the replication group.
The cmdlet compares the replication test file from this reference computer to test files for all other members of the replication group.
If you do not specify this parameter, the cmdlet uses the current computer.

```yaml
Type: String
Parameter Sets: (All)
Aliases: ReferenceMember, RefMem

Required: True
Position: 2
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

### Microsoft.DistributedFileSystemReplication.DfsReplicationGroup, Microsoft.DistributedFileSystemReplication.DfsReplicatedFolder, String

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Remove-DfsrPropagationTestFile](./Remove-DfsrPropagationTestFile.md)

[Start-DfsrPropagationTest](./Start-DfsrPropagationTest.md)

