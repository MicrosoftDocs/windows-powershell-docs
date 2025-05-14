---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: DfsrPowerShell.dll-Help.xml
Module Name: DFSR
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dfsr/grant-dfsrdelegation?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Grant-DfsrDelegation
---

# Grant-DfsrDelegation

## SYNOPSIS
Grants permissions to security principals for a replication group.

## SYNTAX

```
Grant-DfsrDelegation [-GroupName] <String[]> [-AccountName] <String[]> [-Force] [[-DomainName] <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Grant-DfsrDelegation** cmdlet grants users or groups permission to create replicated folders, connections, members, and memberships inside a replication group.
Delegation allows users who are local administrators on servers that run the Distributed File System (DFS) Replication service to administer the Active Directory Domain Services (AD DS) portions of the replication topology, without being domain administrators.

## EXAMPLES

### Example 1: Grant delegated permissions
```
PS C:\> Grant-DfsrDelegation -GroupName "RG01" -AccountName "DFSR Admins"
GroupName   : RG01
AccountName : TSQA\DFSR Admins
IsInherited : False
```

This command grants delegated permissions to the security group named DFSR Admins for a replication group named RG01.

## PARAMETERS

### -AccountName
Specifies an array of names of security principals.
This cmdlet assigns permissions to the users and groups that this parameter specifies.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DomainName
Specifies the NetBIOS name or fully qualified domain name (FQDN) for the AD DS domain that contains a replication group.
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
Shows what would happen if the cmdlet runs. The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.DistributedFileSystemReplication.DfsReplicationGroup, String[], String

## OUTPUTS

### Microsoft.DistributedFileSystemReplication.DfsrDelegation

## NOTES

## RELATED LINKS

[Get-DfsrDelegation](./Get-DfsrDelegation.md)

[Revoke-DfsrDelegation](./Revoke-DfsrDelegation.md)

