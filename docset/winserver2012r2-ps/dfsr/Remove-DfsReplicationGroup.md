---
external help file: DfsrPowerShell.dll-Help.xml
Module Name: DFSR
online version: 
schema: 2.0.0
title: Remove-DfsReplicationGroup
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 1F44314E-D3CE-4C61-88CF-C60671CD235C
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

When you remove a replication group, you remove the group from Active Directory, and you also delete all associated aspects of the DFS Replication topology for that replication group, such as members, memberships, and connections.
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
PS C:\> Remove-DfsReplicationGroup -GroupName "RG*" -RemoveReplicatedFolders -Domain corp.contoso.com -RemoveReplicatedFolders
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
Specifies a NetBIOS or fully qualified domain name (FQDN) for an Active Directory domain that contains the replication group.
If you do not specify this parameter, the cmdlet uses the current domain.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 100
Default value: [Current Domain]
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
You can specify multiple groups, separated by commas, as well as wildcard characters (*).

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.DistributedFileSystemReplication.DfsReplicationGroup

## OUTPUTS

### [none]

## NOTES

## RELATED LINKS

[Get-DfsReplicationGroup](./Get-DfsReplicationGroup.md)

[New-DfsReplicationGroup](./New-DfsReplicationGroup.md)

[Set-DfsReplicationGroup](./Set-DfsReplicationGroup.md)

