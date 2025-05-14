---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: DfsrPowerShell.dll-Help.xml
Module Name: DFSR
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dfsr/set-dfsrconnection?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-DfsrConnection
---

# Set-DfsrConnection

## SYNOPSIS
Changes the settings of a connection between members of a replication group.

## SYNTAX

```
Set-DfsrConnection [[-GroupName] <String[]>] [-SourceComputerName] <String> [-DestinationComputerName] <String>
 [[-DisableConnection] <Boolean>] [[-DisableRDC] <Boolean>] [[-DisableCrossFileRDC] <Boolean>]
 [[-Description] <String>] [[-MinimumRDCFileSizeInKB] <Int64>] [[-DomainName] <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-DfsrConnection** cmdlet changes a connection between two members of a replication group.

Distributed File System (DFS) Replication connections are the logical partnerships between members in a replication group.
The DFS Replication service uses the Remote Procedure Call (RPC) protocol to communicate between servers.
The DFS Replication service does not support modifying connection bandwidth or schedules, which typically do not require changes.

## EXAMPLES

### Example 1: Change a connection between members of a replication group
```
PS C:\> Set-DfsrConnection -GroupName "RG24" -SourceComputerName "SRV01" -DestinationComputerName "SRV02" -DisableRDC $True -DisableCrossFileRDC $True


GroupName               : rg 1
SourceComputerName      : SRV01
DestinationComputerName : SRV02
DomainName              : corp.contoso.com
Identifier              : 8b51a050-f32d-42dc-b008-80f56754f373
Enabled                 : True
RdcEnabled              : False
CrossFileRdcEnabled     : False
Description             :
MinimumRDCFileSizeInKB  : 64
State                   : Normal
```

This command changes the settings of a connection between the computers named SRV01 and SRV02 in the RG24 replication group.
The command specifies that the connection no longer uses Remote Differential Compression or Cross-File RDC from SRV01 to SRV02.
The administrator has determined that the network that connects these servers is a high-bandwidth LAN that should replicate faster than low-bandwidth WAN connections.

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

### -Description
Specifies a description for the connection.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 6
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DestinationComputerName
Specifies the name of the receiving computer.
A receiving computer is also called an inboard or downstream computer.

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

### -DisableConnection
Specifies that the DFS Replication service disables the connection.

You do not typically need to disable a connection.
Specify this parameter to temporarily pause replication.
You can also use the **Suspend-DfsReplicationGroup** cmdlet to halt replication between computers.
You must enable a connection between the computers before the DFS Replication service can initiate replication.

Important: Specify this parameter instead of disabling a computer's membership in the replication group by using the **Set-DfsrMembership** cmdlet.
Disabling and enabling the membership of a computer causes non-authoritative inbound replication.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableCrossFileRDC
Indicates that the DFS Replication service disables the cross-file similarity Remote Differential Compression (RDC) algorithm on this connection.

Cross-file RDC uses up to five existing previously replicated files on a volume to seed a new replicating file.
Applying cross-file RDC over very low-bandwidth network connections with files that are very similar results in very large bandwidth savings and potentially large time savings.
When you use cross-file RDC on very high-bandwidth network connections, cross-file RDC may add too much local processing time and negatively affect performance.
In extremely large datasets (millions of files on a volume with a great deal of similarity), cross-file RDC may also negatively affect CPU and disk utilization.
Consider disabling cross-file RDC when you replicate over LANs and very high performance WANs.
This setting is only supported on Windows Server 2012 R2 and later.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: 5
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableRDC
Indicates that the DFS Replication service creates the connection with Remote Differential Compression (RDC) disabled.

You do not typically need to specify this parameter when you use lower bandwidth, higher latency connections.
Consider specifying this parameter if the connection is over a LAN or very high performance WAN connection.
By default, RDC is enabled on DFS Replication connections.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: 4
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

### -GroupName
Specifies an array of names of replication groups.
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

### -MinimumRDCFileSizeInKB
Specifies the file size threshold, in Kilobytes, for RDC to apply.

You do not typically need to specify this parameter when you use lower bandwidth/higher latency connections.
Consider specifying this parameter only if the connection is over a LAN or a very high performance WAN connection.
By default, any files equal to or greater than 64KB are chunked by RDC.

```yaml
Type: Int64
Parameter Sets: (All)
Aliases:

Required: False
Position: 7
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
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

### Microsoft.DistributedFileSystemReplication.DfsReplicationGroup

## OUTPUTS

### Microsoft.DistributedFileSystemReplication.DfsrConnection, String

## NOTES

## RELATED LINKS

[Get-DfsrConnection](./Get-DfsrConnection.md)

[Add-DfsrConnection](./Add-DfsrConnection.md)

[Remove-DfsrConnection](./Remove-DfsrConnection.md)

