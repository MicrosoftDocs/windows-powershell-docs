---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: DfsrPowerShell.dll-Help.xml
Module Name: DFSR
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dfsr/remove-dfsrmember?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-DfsrMember
---

# Remove-DfsrMember

## SYNOPSIS
Removes computers from a replication group.

## SYNTAX

```
Remove-DfsrMember [-GroupName] <String[]> [-ComputerName] <String[]> [-Force] [[-DomainName] <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-DfsrMember** cmdlet removes member computers from a replication group.
Members of a replication group host replicated folders.
If you remove a member from its replication group, Distributed File System (DFS) Replication stops replication on that member.
This cmdlet does not delete the contents of replicated folders or their private data.
Use the Add-DfsrMember to add member computers to a group.

## EXAMPLES

### Example 1: Remove a member from a group
```
PS C:\> Remove-DfsrMember -GroupName "River Branch Office" -ComputerName "SRV02"
This operation will remove the computer and all of its memberships and connections.
Computer: SRV02 Replication group:"River Branch Office"
Are you sure you want to continue to remove this computer from its replication group and all of its memberships and
connections?
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"):
```

This command removes the member computer named SRV02 from the River Branch Office replication group.
Because this example does not include the *Force* parameter, the command prompts you for confirmation.

### Example 2: Remove all members from a group
```
PS C:\> Remove-DfsrMember -GroupName "RG07" -ComputerName * -Force
```

This command removes all the member computers from the replication group named RG07.
Because the command includes the *Force* parameter, it removes the members without prompting for confirmation.

## PARAMETERS

### -ComputerName
Specifies an array of names of member computers.
The cmdlet removes these members from the replication group.
You can use a comma separated list and the wildcard character (*).

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: MemberList, MemList

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
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

### Microsoft.DistributedFileSystemReplication.DfsReplicationGroup

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Add-DfsrMember](./Add-DfsrMember.md)

[Get-DfsrMember](./Get-DfsrMember.md)

[Set-DfsrMember](./Set-DfsrMember.md)

