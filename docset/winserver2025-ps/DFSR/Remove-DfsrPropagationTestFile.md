---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: DfsrPowerShell.dll-Help.xml
Module Name: DFSR
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dfsr/remove-dfsrpropagationtestfile?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-DfsrPropagationTestFile
---

# Remove-DfsrPropagationTestFile

## SYNOPSIS
Removes DFS Replication propagation test files.

## SYNTAX

```
Remove-DfsrPropagationTestFile [-GroupName] <String[]> [-FolderName] <String[]> [[-ComputerName] <String>]
 [-AgeInDays] <UInt32> [-Force] [[-DomainName] <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-DfsrPropagationTestFile** cmdlet removes test files from a Distributed File System (DFS) Replication replicated folder.
Once you remove the file from one member computer in a replication group, DFS Replication removes the file from all other members.
To create test files, use the **Start-DfsrPropagationTest** cmdlet.

Test files contain only test metadata.
You can remove them at any time.

## EXAMPLES

### Example 1: Remove all test files from a specified replicated folder
```
PS C:\> Remove-DfsrPropagationTestFile -GroupName "RG01" -FolderName "RF07" -ComputerName "SRV01" -AgeInDays 0
This operation will remove the propagation test files from the computer named "SRV01" that are more than 0 days old.
Are you sure you want to continue to remove this propagation test file?
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"):
```

This command removes all propagation test files from the RF07 folder on the computer named SRV01.
This computer is part of the group named RG01.
The value of zero (0) for the *AgeInDays* parameter causes the command to remove all test files, no matter how long ago you created them.
The command does not include the *Force* parameter, so you must confirm the removal.

## PARAMETERS

### -AgeInDays
Specifies the age, in days, of propagation test files to delete.
To delete propagation files created within the past 24 hours or to delete all propagation test files, set this value to zero (0).

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
Specifies the name of a replication member computer.
If you do not specify this parameter, the cmdlet uses the current computer.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Member, Mem

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

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
If you do not specify this parameter, the cmdlet removes test files from all replicated folders.

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

### -Force
Forces the command to run without asking for user confirmation.

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

### -GroupName
Specifies an array of names of replication groups.
You can use a comma separated list and the wildcard character (*).
If you do not specify this parameter, the cmdlet removes test files from replicated folders for all groups within the specified domain.

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

### Microsoft.DistributedFileSystemReplication.DfsReplicationGroup, Microsoft.DistributedFileSystemReplication.DfsReplicatedFolder, string

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Start-DfsrPropagationTest](./Start-DfsrPropagationTest.md)

[Write-DfsrPropagationReport](./Write-DfsrPropagationReport.md)

