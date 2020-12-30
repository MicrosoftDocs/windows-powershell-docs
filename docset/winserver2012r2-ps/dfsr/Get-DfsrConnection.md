---
external help file: DfsrPowerShell.dll-Help.xml
Module Name: DFSR
online version: 
schema: 2.0.0
title: Get-DfsrConnection
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
ms.assetid: 30DD9BEA-57E4-41F9-A418-0933E227381F
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
The **Get-DfsrConnection** cmdlet gets an existing connection between two DFS Replication partners.

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
Default value: [Current Domain]
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
Accept wildcard characters: False
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
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.DistributedFileSystemReplication.DfsReplicationGroup

## OUTPUTS

### Microsoft.DistributedFileSystemReplication.DfsrConnection

## NOTES

## RELATED LINKS

[Add-DfsrConnection](./Add-DfsrConnection.md)

[Set-DfsrConnection](./Set-DfsrConnection.md)

[Remove-DfsrConnection](./Remove-DfsrConnection.md)

