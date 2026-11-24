---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: DfsrPowerShell.dll-Help.xml
Module Name: DFSR
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dfsr/get-dfsreplicatedfolder?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-DfsReplicatedFolder
---

# Get-DfsReplicatedFolder

## SYNOPSIS
Gets a replicated folder from a replication group.

## SYNTAX

```
Get-DfsReplicatedFolder [[-GroupName] <String[]>] [[-FolderName] <String[]>] [[-DomainName] <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-DfsReplicatedFolder** cmdlet gets existing replicated folders.
The cmdlet returns global settings of replicated folders such as filters and Distributed File System (DFS) Namespace associations.
Replicated folders are logical arrangements of replication that do not contain computer-specific settings.

## EXAMPLES

### Example 1: Get a replicated folder
```
PS C:\> Get-DfsReplicatedFolder -GroupName "RG24" -FolderName "RF01"


GroupName              : RG24
DomainName             : corp.contoso.com
FolderName             : RF01
Identifier             : c335e8f6-bc3e-4671-8f7b-9cdc51a6b222
Description            :
FileNameToExclude      : {~*, *.bak, *.tmp}
DirectoryNameToExclude : {}
DfsnPath               :
IsDfsnPathPublished    : False
State                  : Normal
```

This command gets the replicated folder named RF01 from replication group named RG24.

## PARAMETERS

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

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.DistributedFileSystemReplication.DfsReplicationGroup

## OUTPUTS

### Microsoft.DFSR.Management.ReplicatedFolder

## NOTES

## RELATED LINKS

[Set-DfsReplicatedFolder](./Set-DfsReplicatedFolder.md)

[Set-DfsReplicatedFolder](./Set-DfsReplicatedFolder.md)

[Remove-DfsReplicatedFolder](./Remove-DfsReplicatedFolder.md)

