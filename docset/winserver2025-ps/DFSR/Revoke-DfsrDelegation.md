---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: DfsrPowerShell.dll-Help.xml
Module Name: DFSR
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dfsr/revoke-dfsrdelegation?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Revoke-DfsrDelegation
---

# Revoke-DfsrDelegation

## SYNOPSIS
Revokes permissions to security principals for a replication group.

## SYNTAX

```
Revoke-DfsrDelegation [-GroupName] <String[]> [-AccountName] <String[]> [-Force] [[-DomainName] <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Revoke-DfsrDelegation** cmdlet revokes delegated permissions for users or groups for a replication group.
For more information about delegation in the Distributed File System (DFS) Replication service, see the documentation for the **Grant-DfsrDelegation** cmdlet.

## EXAMPLES

### Example 1: Revoke delegated permissions
```
PS C:\> Revoke-DfsrDelegation -GroupName "RG01" -AccountName "DFSR Admins"
This operation will revoke delegation of permissions on the replication group named "RG01" for the account named DFSR
Admins.
Are you sure you want to revoke delegation of permissions on this replication group?
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"):
```

This command revokes delegated permissions for the security group named DFSR Admins for a replication group named RG01.

### Example 2: Revoke delegated permissions without confirmation
```
PS C:\> Revoke-DfsrDelegation -GroupName "RG02 -AccountName "DFSR Admins" -Verbose -Force
VERBOSE: Performing the operation "Revoke-DfsrDelegation" on target "RG02".
VERBOSE: Successfully revoked delegation of permissions on the replication group named "RG02" for the account named
DFSR Admins
```

This command revokes delegated permissions for the security group named DFSR Admins for a replication group named RG02.
This command specifies the *Force* parameter, and, therefore, it does not prompt you to confirm the removal.
The command specifies the **Verbose** common parameter, so it prints details of the operation.

## PARAMETERS

### -AccountName
Specifies an array of names of security principals.
This cmdlet revokes permissions to the users and groups that this parameter specifies.

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

[Grant-DfsrDelegation](./Grant-DfsrDelegation.md)

