---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: DfsrPowerShell.dll-Help.xml
Module Name: DFSR
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dfsr/set-dfsrmember?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-DfsrMember
---

# Set-DfsrMember

## SYNOPSIS
Modifies member computer information in a replication group.

## SYNTAX

```
Set-DfsrMember [-GroupName] <String[]> [-ComputerName] <String[]> [[-Description] <String>]
 [[-DomainName] <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-DfsrMember** cmdlet modifies member computer information in a replication group.
Members of a replication group host replicated folders.
You can modify the description of a member.

## EXAMPLES

### Example 1: Update the description for a member
```
PS C:\> Set-DfsrMember -GroupName "RG07" -Member "SRV01" -Description "Waukegan Branch Office Server"
GroupName                    : RG07
ComputerName                 : SRV01
DomainName                   : corp.contoso.com
Identifier                   : 5ddc94cd-1602-477d-9e50-a66af5892b67
Description                  : Waukegan Branch Office Server
DnsName                      : SRV01.corp.contoso.com
Site                         : Default-First-Site-Name
NumberOfConnections          : 2
NumberOfInboundConnections   : 1
NumberOfOutboundConnections  : 1
NumberOfInterSiteConnections : -2
NumberOfIntraSiteConnections : 2
IsClusterNode                : True
State                        : Normal
```

This command updates the description for the computer named SRV01 in the group named RG07.
The console displays the **DfsrMember** object, which includes the updated description.

## PARAMETERS

### -ComputerName
Specifies an array of names of member computers.
You can use a comma separated list and the wildcard character (*).

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: MemberList, MemList

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### -Description
Specifies a description for a member computer.

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

### -DomainName
Specifies the NetBIOS name or fully qualified domain name (FQDN) for the Active Directory Domain Service (AD DS) domain that contains a replication group.
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
You can use a comma separated list and the wildcard character (*).
If you do not specify this parameter, the cmdlet uses all participating replication groups.

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

### Microsoft.DistributedFileSystemReplication.DfsReplicationGroup, String

## OUTPUTS

### Microsoft.DistributedFileSystemReplication.DfsrMember

## NOTES

## RELATED LINKS

[Add-DfsrMember](./Add-DfsrMember.md)

[Get-DfsrMember](./Get-DfsrMember.md)

[Remove-DfsrMember](./Remove-DfsrMember.md)

