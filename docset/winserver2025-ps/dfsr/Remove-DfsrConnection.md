---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: DfsrPowerShell.dll-Help.xml
Module Name: DFSR
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dfsr/remove-dfsrconnection?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-DfsrConnection
---

# Remove-DfsrConnection

## SYNOPSIS
Removes a connection between members of a replication group.

## SYNTAX

```
Remove-DfsrConnection [-GroupName] <String[]> [-SourceComputerName] <String>
 [-DestinationComputerName] <String> [-Force] [[-DomainName] <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Remove-DfsrConnection** cmdlet removes a connection between members of a replication group.
After you remove the connections between a pair of server, the Distributed File System (DFS) Replication service cannot replicate data between the servers.
You should always delete connections bidirectionally between two servers.
Run this cmdlet for the receiving computer and the sending computer.

DFS Replication connections are the logical partnerships between members in a replication group.
The DFS Replication service uses the Remote Procedure Call (RPC) protocol to communicate between servers.

## EXAMPLES

### Example 1: Remove a connection between members of a replication group
```
PS C:\> Remove-DfsrConnection -GroupName "RG24" -SourceComputerName "SRV01" -DestinationComputerName "SRV02"
This operation will remove the connection from the replication group. First computer: SRV01 Second computer: SRV02 Replication group: "RG24"
Are you sure you want to continue to remove this connection?
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): y
```

This command removes the connection from the computer named SRV01 to the computer named SRV02 in the replication group named RG24.

### Example 2: Remove a connection between members of a replication group without a confirmation
```
PS C:\> Remove-DfsrConnection -GroupName "RG24" -SourceComputerName "SRV02" -DestinationComputerName "SRV01" -Force
```

This command removes the connection from the computer named SRV01 to the computer named SRV02 without prompting you to confirm the removal.

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

### -DestinationComputerName
Specifies the name of the receiving computer.
A receiving computer is also called an inbound or downstream computer.

```yaml
Type: String
Parameter Sets: (All)
Aliases: ReceivingMember, RMem

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
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
Position: 3
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
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### -SourceComputerName
Specifies the name of the sending computer.
A sending computer is also called an outbound or upstream computer.

```yaml
Type: String
Parameter Sets: (All)
Aliases: SendingMember, SMem

Required: True
Position: 1
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

[Get-DfsrConnection](./Get-DfsrConnection.md)

[Add-DfsrConnection](./Add-DfsrConnection.md)

[Set-DfsrConnection](./Set-DfsrConnection.md)

