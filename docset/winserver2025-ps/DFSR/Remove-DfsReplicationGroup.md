---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: DfsrPowerShell.dll-Help.xml
Module Name: DFSR
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dfsr/remove-dfsreplicationgroup?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-DfsReplicationGroup
---

# Remove-DfsReplicationGroup

## SYNOPSIS
Removes a replication group.

## SYNTAX

```
Remove-DfsReplicationGroup [-GroupName] <String[]> [-RemoveReplicatedFolders] [-Force] [[-DomainName] <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-DfsReplicationGroup** cmdlet removes a replication group.

When you remove a replication group, you remove the group from Active Directory, and you also delete all associated aspects of the Distributed File System (DFS) Replication topology for that replication group, such as members, memberships, and connections.
All replication halts on all members.
This operation does not delete any replicated file data or private data.
Use this command only when you decommission a replication group.

## EXAMPLES

### Example 1: Remove a replication group
```
PS C:\> Remove-DfsReplicationGroup -GroupName "RG01"
Performing this operation will remove the replication group "RG01" and the subscriptions members have to this
replication group. Are you sure you want to continue to remove this replication group? [Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): y
```

This command removes the replication group named RG01 from the current domain.

### Example 2: Remove replication groups using a wildcard
```
PS C:\> Remove-DfsReplicationGroup -GroupName "RG*" -RemoveReplicatedFolders -Domain "corp.contoso.com"
Performing this operation will remove the replication group "RG01" and the subscriptions members have to this
replication group. Are you sure you want to continue to remove this replication group? [Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"):

Performing this operation will remove the replication group "RG02" and the subscriptions members have to this
replication group. Are you sure you want to continue to remove this replication group? [Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"):

Performing this operation will remove the replication group "RG03" and the subscriptions members have to this
replication group. Are you sure you want to continue to remove this replication group? [Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"):
```

This command removes all replication groups that include the pattern RG* in domain corp.contoso.com, even if the groups include replicated folders.

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
Specifies the NetBIOS name or fully qualified domain name (FQDN) for the Active Directory Domain Service (AD DS) domain that contains a replication group..
If you do not specify this parameter, the cmdlet uses the current domain.

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

### -Force
Forces the command to run without asking for user confirmation.
Use this parameter for scripted removal of replication groups.

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

If the replication group contains any replicated folders, you must specify the **RemoveReplicatedFolders** switch parameter.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: RG, RgName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -RemoveReplicatedFolders
Indicates that the cmdlet removes any replicated folders belonging to the replication group prior to deleting the replication group.

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

### [none]

## NOTES

## RELATED LINKS

[Get-DfsReplicationGroup](./Get-DfsReplicationGroup.md)

[New-DfsReplicationGroup](./New-DfsReplicationGroup.md)

[Set-DfsReplicationGroup](./Set-DfsReplicationGroup.md)

