---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: DfsrPowerShell.dll-Help.xml
Module Name: DFSR
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dfsr/remove-dfsreplicatedfolder?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-DfsReplicatedFolder
---

# Remove-DfsReplicatedFolder

## SYNOPSIS
Removes a replicated folder from a replication group.

## SYNTAX

```
Remove-DfsReplicatedFolder [-GroupName] <String[]> [-FolderName] <String[]> [-Force] [[-DomainName] <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-DfsReplicatedFolder** cmdlet removes replicated folders from a replication group.
Replicated folders are logical arrangements of replication that do not contain computer-specific settings.

When you remove a replicated folder, the Distributed File System (DFS) Replication service cannot replicate the folder.
This operation does not delete any replicated file data.
Use this cmdlet only when you decommission a replicated folder.

## EXAMPLES

### Example 1: Remove a replicated folder
```
PS C:\> Remove-DfsReplicatedFolder -GroupName "RG11" -FolderName "RF22"

Performing this operation will remove the replicated folder "RF22" and its memberships.
Are you sure you want to continue to remove this replicated folder and its memberships?
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): y
```

This command removes the replicated folder RF22 and its associated memberships from the replication group named RG11.

### Example 2: Remove all replicated folders associated with a replication group
```
PS C:\> Remove-DfsReplicatedFolder -GroupName "RG11" -FolderName * -Force
```

This command removes all replicated folders and their associated memberships from the replication group named RG11.
The *Force* parameter specifies that the cmdlet does not prompt you to confirm that you want to remove each replicated folder.

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
If you do not specify this parameter, the cmdlet gets all replicated folders.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: RF, RfName

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### -Force
Forces the command to run without asking for user confirmation.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
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

### Microsoft.DistributedFileSystemReplication.DfsReplicationGroup, string

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Get-DfsReplicatedFolder](./Get-DfsReplicatedFolder.md)

[Set-DfsReplicatedFolder](./Set-DfsReplicatedFolder.md)

[New-DfsReplicatedFolder](./New-DfsReplicatedFolder.md)

