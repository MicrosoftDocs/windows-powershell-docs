---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: DfsrPowerShell.dll-Help.xml
Module Name: DFSR
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dfsr/get-dfsrconnection?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-DfsrConnection
---

# Get-DfsrConnection

## SYNOPSIS
Gets a connection between DFS Replication partners.

## SYNTAX

```
Get-DfsrConnection [[-GroupName] <String[]>] [[-SourceComputerName] <String>]
 [[-DestinationComputerName] <String>] [[-DomainName] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-DfsrConnection** cmdlet gets an existing connection between two Distributed File System (DFS) Replication partners.

DFS Replication connections are the logical partnerships between members in a replication group.
The DFS Replication service uses the Remote Procedure Call (RPC) protocol to communicate between servers.

## EXAMPLES

### Example 1: Get a one-way connection between computers
```
PS C:\> Get-DfsrConnection -GroupName "RG24" -SourceComputerName "SRV01" -DestinationComputerName "SRV02"


GroupName               : RG24
SourceComputerName      : SRV01
DestinationComputerName : SRV02
DomainName              : corp.contoso.com
Identifier              : c33eaaf1-9e50-4510-8484-68271bf93b25
Enabled                 : True
RdcEnabled              : True
CrossFileRdcEnabled     : True
Description             :
MinimumRDCFileSizeInKB  : 64
State                   : Normal
```

This command gets the one-way connection from the computer named SRV01 to the computer named SRV02 in the RG24 replication group.

## PARAMETERS

### -DestinationComputerName
Specifies the name of the receiving computer.
A receiving computer is also called an inbound or downstream computer.

```yaml
Type: String
Parameter Sets: (All)
Aliases: ReceivingMember, RMem

Required: False
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

### -SourceComputerName
Specifies the name of the sending computer.
A sending computer is also called an outbound or upstream computer.

```yaml
Type: String
Parameter Sets: (All)
Aliases: SendingMember, SMem

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.DistributedFileSystemReplication.DfsReplicationGroup

## OUTPUTS

### Microsoft.DistributedFileSystemReplication.DfsrConnection

## NOTES

## RELATED LINKS

[Add-DfsrConnection](./Add-DfsrConnection.md)

[Set-DfsrConnection](./Set-DfsrConnection.md)

[Remove-DfsrConnection](./Remove-DfsrConnection.md)

