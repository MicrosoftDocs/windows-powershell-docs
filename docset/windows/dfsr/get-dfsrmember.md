---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-anbarr
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: DfsrPowerShell.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-DfsrMember
ms.reviewer:
ms.assetid: E69136B5-F04A-4F5C-BC8A-C6F01F26D5D4
---

# Get-DfsrMember

## SYNOPSIS
Gets member computers in a replication group.

## SYNTAX

```
Get-DfsrMember [[-GroupName] <String[]>] [[-ComputerName] <String[]>] [[-DomainName] <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-DfsrMember** cmdlet gets member computers in a replication group.
Members of a replication group host replicated folders.

## EXAMPLES

### Example 1: Get a member in a replication group
```
PS C:\> Get-DfsrMember -GroupName "RG07" -ComputerName "SRV01"

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
IsClusterNode                : False
State                        : Normal
```

This command gets the member computer named SRV01 that belongs to the group named RG07.

## PARAMETERS

### -ComputerName
Specifies an array of names of member computers.
You can use a comma separated list and the wildcard character (*).
If you do not specify this parameter, the cmdlet gets all members of replication groups specified by using the **DomainName** and **GroupName** parameters.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: MemberList, MemList

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
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

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.DistributedFileSystemReplication.DfsReplicationGroup

## OUTPUTS

### Microsoft.DistributedFileSystemReplication.DfsrMember

## NOTES

## RELATED LINKS

[Add-DfsrMember](./Add-DfsrMember.md)

[Remove-DfsrMember](./Remove-DfsrMember.md)

[Set-DfsrMember](./Set-DfsrMember.md)

