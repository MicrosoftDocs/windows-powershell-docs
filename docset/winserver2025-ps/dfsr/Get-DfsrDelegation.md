---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: DfsrPowerShell.dll-Help.xml
Module Name: DFSR
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dfsr/get-dfsrdelegation?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-DfsrDelegation
---

# Get-DfsrDelegation

## SYNOPSIS
Gets principals that have permissions for a replication group.

## SYNTAX

```
Get-DfsrDelegation [[-GroupName] <String[]>] [[-DomainName] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-DfsrDelegation** cmdlet gets the users and groups that have permission to create replicated folders, connections, members, and memberships for a replication group.
For more information about delegation in the Distributed File System (DFS) Replication service, see the documentation for the **Grant-DfsrDelegation** cmdlet.

## EXAMPLES

### Example 1: Get principals for a replication group
```
PS C:\> Get-DfsrDelegation -GroupName "RG01"

GroupName   : RG01
AccountName : NT AUTHORITY\SYSTEM
IsInherited : False

GroupName   : RG01
AccountName : TSQA\Domain Admins
IsInherited : False

GroupName   : RG01
AccountName : TSQA\DFSR Admins
IsInherited : False

GroupName   : RG01
AccountName : TSQA\Enterprise Admins
IsInherited : True
```

This command gets the users and groups that have delegated permissions for the replication group named RG01.

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

### -GroupName
Specifies an array of names of replication groups.

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

### Microsoft.DistributedFileSystemReplication.DfsReplicationGroup, String[], String

## OUTPUTS

### Microsoft.DistributedFileSystemReplication.DfsrDelegation

## NOTES

## RELATED LINKS

[Grant-DfsrDelegation](./Grant-DfsrDelegation.md)

[Revoke-DfsrDelegation](./Revoke-DfsrDelegation.md)

