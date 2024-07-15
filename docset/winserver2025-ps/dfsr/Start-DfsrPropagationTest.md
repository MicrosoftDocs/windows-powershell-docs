---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: DfsrPowerShell.dll-Help.xml
Module Name: DFSR
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dfsr/start-dfsrpropagationtest?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Start-DfsrPropagationTest
---

# Start-DfsrPropagationTest

## SYNOPSIS
Creates a propagation test file in a replicated folder.

## SYNTAX

```
Start-DfsrPropagationTest [[-GroupName] <String[]>] [-FolderName] <String[]> [-ReferenceComputerName] <String>
 [[-DomainName] <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Start-DfsrPropagationTest** cmdlet creates a propagation test file in a Distributed File System (DFS) replicated folder.
The test file contains metadata, such as time and date stamps.
The DFS Replication service propagates the file to other computers in the replication group.
You can create propagation reports by using the **Write-DfsrPropagationReport** cmdlet.

This cmdlet creates test files in replicated folders in a hidden, read-only system folder named __DFSR_DIAGNOSTICS_TEST_FOLDER__.
The cmdlet names the test files \<Reference Computer Name\>@\<GUID\>@\<RG Name\>-\<RF Name\>.xml.
Use the **Remove-DfsrPropagationTestFile** cmdlet to delete old test files.

## EXAMPLES

### Example 1: Create a test file on a specified reference computer
```
PS C:\> Start-DfsrPropagationTest -GroupName "ReplicationGroup07" -FolderName "ReplicatedFolder19" -ReferenceComputerName "SRV01.Contoso.com"
```

This command creates a propagation test file for the replicated folder named ReplicatedFolder19 in the group named ReplicationGroup07.
The command specifies a reference computer name.

### Example 2: Create test files for all replicated folders
```
PS C:\> Start-DfsrPropagationTest -GroupName * -FolderName * -ReferenceComputerName "SRV01.corp.Contoso.com" -Verbose
VERBOSE: Performing operation "Start-DfsrPropagationTest" on Target "DFSR membership with domain: corp.contoso.com;
replication group: RG 1; replicated folder: RF 1; computer: SRV01; GUID: {966e2e84-7792-438f-8344-c8f76d214d06}.".
VERBOSE: Successfully started the propagation test for DFSR membership with domain: corp.contoso.com; replication
group: RG 1; replicated folder: RF 1; computer: SRV01; GUID: {966e2e84-7792-438f-8344-c8f76d214d06}.
VERBOSE: Performing operation "Start-DfsrPropagationTest" on Target "DFSR membership with domain: corp.contoso.com;
replication group: Branch Office 1; replicated folder: Data Distribution 1; computer: SRV01; GUID:
{dbaa3a16-f731-4428-8a4f-8278673e848a}.".
VERBOSE: Successfully started the propagation test for DFSR membership with domain: corp.contoso.com; replication
group: Branch Office 1; replicated folder: Data Distribution 1; computer: SRV01; GUID:
{dbaa3a16-f731-4428-8a4f-8278673e848a}.
```

This command creates test files in all replicated folders on the reference computer named SRV01.corp.Contoso.com.
The command uses the wildcard character (*) for the **GroupName** and **FolderName** parameter values, and, therefore, it creates a test file in any replicated folder on the computer, regardless of what replication group or groups the computer might be a member of.

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

### -FolderName
Specifies an array of names of replicated folders.
You can use a comma separated list and the wildcard character (*).
If you do not specify this parameter, the cmdlet creates test files for all replicated folders within the specified group and domain.

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
You can use a comma separated list and the wildcard character (*).
If you do not specify this parameter, the cmdlet creates test files for all replicated folders that have name that matches the value of the *FolderName* parameter within the specified domain.

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

### -ReferenceComputerName
Specifies the name of a reference computer in the replication group.
The cmdlet creates the propagation test file on the reference computer.
If you do not specify this parameter, the cmdlet uses the local computer as the reference computer.

```yaml
Type: String
Parameter Sets: (All)
Aliases: ReferenceMember, RefMem

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
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

### [none]

## NOTES

## RELATED LINKS

[Remove-DfsrPropagationTestFile](./Remove-DfsrPropagationTestFile.md)

[Write-DfsrPropagationReport](./Write-DfsrPropagationReport.md)

