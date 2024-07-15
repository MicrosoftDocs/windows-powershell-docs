---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: DfsrPowerShell.dll-Help.xml
Module Name: DFSR
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dfsr/set-dfsreplicatedfolder?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-DfsReplicatedFolder
---

# Set-DfsReplicatedFolder

## SYNOPSIS
Changes settings of a replicated folder.

## SYNTAX

```
Set-DfsReplicatedFolder [-GroupName] <String[]> [[-FolderName] <String[]>] [[-Description] <String>]
 [[-FileNameToExclude] <String[]>] [[-DirectoryNameToExclude] <String[]>] [[-DfsnPath] <String>]
 [[-DomainName] <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-DfsReplicatedFolder** cmdlet changes settings of a replicated folder in a replication group.
You can use this cmdlet to modify global settings of replicated folders such as filters and Distributed File System (DFS) Namespace associations.
Replicated folders are logical arrangements of replication that do not contain computer-specific settings.

## EXAMPLES

### Example 1: Add a description to a replicated folder
```
PS C:\> Set-DfsReplicatedFolder -GroupName "RG11" -FolderName "RF101" -Description "Branch Store #101, Data Collection for Backups"
GroupName              : RG11
FolderName             : RF101
DomainName             : corp.contoso.com
Identifier             : c335e8f6-bc3e-4671-8f7b-9cdc51a6b222
Description            : Branch Store #101 Data Collection for Backups
FileNameToExclude      : {~*, *.bak, *.tmp}
DirectoryNameToExclude : {}
DfsnPath               :
IsDfsnPathPublished    : False
State                  : Normal
```

This command sets a new description on the replicated folder named RF101 in the replication group named RG11.

### Example 2: Exclude files on all replicated folders
```
PS C:\> Set-DfsReplicatedFolder -GroupName "RG11" -FolderName * -FileNameToExclude "~*, *.bak, *.tmp, *.ned"
GroupName              : RG11
FolderName             : RF11
DomainName             : corp.contoso.com
Identifier             : c335e8f6-bc3e-4671-8f7b-9cdc51a6b222
Description            :
FileNameToExclude      : {~*, *.bak, *.tmp, *.ned}
DirectoryNameToExclude : {}
DfsnPath               :
IsDfsnPathPublished    : False
State                  : Normal

GroupName              : RG11
FolderName             : rf12
DomainName             : corp.contoso.com
Identifier             : 50e057af-08a4-4dbb-af1c-3765620afd9e
Description            :
FileNameToExclude      : {~*, *.bak, *.tmp, *.ned}
DirectoryNameToExclude : {}
DfsnPath               :
State                  : Normal

IsDfsnPathPublished    : False

GroupName              : RG11
FolderName             : rf101
DomainName             : corp.contoso.com
Identifier             : c335e8f6-bc3e-4671-8f7b-9cdc51a6b222
Description            : Branch Store #101 Data Collection for Backups
FileNameToExclude      : {~*, *.bak, *.tmp, *.ned}
DirectoryNameToExclude : {}
DfsnPath               :
IsDfsnPathPublished    : False
State                  : Normal
```

This command sets the list of files to exclude from replication for all replicated folders in the RG11 replication group.
The command specifies that the DFS Replication service exclude file names starting with a tilde (~) character and files that have the extensions .bak, .tmp, and .ned from replication.

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

### -Description
Specifies a description for the replicated folder.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DfsnPath
Specifies the DFS Namespace folder path of the replicated folder.

This parameter is used to connect the replication group to the replicated folder.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 5
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DirectoryNameToExclude
Specifies an array of names of subfolders that the DSFR service excludes and does not replicate in the replicated folder.
You must provide only folder names, not full paths.
You can use wildcards.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: DirectoryFilter

Required: False
Position: 4
Default value: None
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

### -FileNameToExclude
Specifies an array of names and extensions of files that the DSFR service excludes and does not replicate.
You must provide only file names, not full paths.
You can use wildcards.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: FileFilter

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FolderName
Specifies an array of names of replicated folders.
You can use a comma separated list and the wildcard character (*).
If you do not specify this parameter, the cmdlet gets all replicated folders.

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

### Microsoft.DistributedFileSystemReplication.DfsReplicationGroup, Microsoft.DistributedFileSystemReplication.DfsReplicatedFolder

## OUTPUTS

### Microsoft.DistributedFileSystemReplication.DfsReplicatedFolder

## NOTES

## RELATED LINKS

[Get-DfsReplicatedFolder](./Get-DfsReplicatedFolder.md)

[New-DfsReplicatedFolder](./New-DfsReplicatedFolder.md)

[Remove-DfsReplicatedFolder](./Remove-DfsReplicatedFolder.md)

