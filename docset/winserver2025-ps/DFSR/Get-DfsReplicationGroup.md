---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: DfsrPowerShell.dll-Help.xml
Module Name: DFSR
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dfsr/get-dfsreplicationgroup?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-DfsReplicationGroup
---

# Get-DfsReplicationGroup

## SYNOPSIS
Retrieves a replication group.

## SYNTAX

```
Get-DfsReplicationGroup [[-GroupName] <String[]>] [-IncludeSysvol] [[-DomainName] <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-DfsReplicationGroup** cmdlet retrieves existing replication groups.

A replication group is a set of servers, or members, that participate in the replication of one or more folders.
A replicated folder is kept synchronized among the members of a replication group.
The Distributed File System (DFS) Replication Get-* cmdlets are useful for pipeline operations or inventory.

## EXAMPLES

### Example 1: Retrieve replication groups
```
PS C:\> Get-DfsReplicationGroup -GroupName RG02
GroupName              : RG02
DomainName             : corp.contoso.com
Identifier             : 81251362-e30f-4c1e-b6b0-23906c1ebdd7
Description            :
State                  : Normal
```

This command retrieves the RG02 replication group for inventory or use in other pipelines.

### Example 2: Retrieve replication groups and SYSVOL shared volume
```
PS C:\> Get-DfsReplicationGroup -GroupName * -IncludeSysvol
GroupName              : Domain System Volume
DomainName             : corp.contoso.com
Identifier             : a8ff93e7-aab3-4330-ab66-dcab60dd9d1b
Description            :
State                  : Normal

GroupName              : RG02
DomainName             : corp.contoso.com
Identifier             : 81251362-e30f-4c1e-b6b0-23906c1ebdd7
Description            :
State                  : Normal

GroupName              : RG3
DomainName             : corp.contoso.com
Identifier             : 075a5be7-ef53-455d-9c27-0a2ffe6f688a
Description            :
State                  : Normal
```

This command retrieves all replication groups for inventory, including the special Domain System Volume resource group created by domain controllers.
By default, this resource group is not returned as its management is controlled by Active Directory.

## PARAMETERS

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

### -IncludeSysvol
Indicates that the cmdlet retrieves the special Domain System Volume replication group that domain controllers create.
This replication group contains the SYSVOL Share replicated folder.
DFS Replication does not allow direct modification of SYSVOL due to internal blocks, and this parameter is provided for convenience only so that administrators can inventory if a domain contains DFSR SYSVOL.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### String

## OUTPUTS

### Microsoft.DistributedFileSystemReplication.DfsReplicationGroup
This cmdlet returns an object that contains the properties of a DFS Replication group.

## NOTES

## RELATED LINKS

[New-DfsReplicationGroup](./New-DfsReplicationGroup.md)

[Remove-DfsReplicationGroup](./Remove-DfsReplicationGroup.md)

[Set-DfsReplicationGroup](./Set-DfsReplicationGroup.md)

[Suspend-DfsReplicationGroup](./Suspend-DfsReplicationGroup.md)

[Sync-DfsReplicationGroup](./Sync-DfsReplicationGroup.md)

