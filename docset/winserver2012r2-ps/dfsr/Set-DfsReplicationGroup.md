---
external help file: DfsrPowerShell.dll-Help.xml
Module Name: DFSR
online version: 
schema: 2.0.0
title: Set-DfsReplicationGroup
ms.author: kenwith
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: kenwith
manager: jasgro
ms.date: 2017-10-30
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 209C030C-4BAE-4EBD-BE47-EE945F322E82
---

# Set-DfsReplicationGroup

## SYNOPSIS
Modifies a replication group.

## SYNTAX

```
Set-DfsReplicationGroup [-GroupName] <String[]> [[-Description] <String>] [[-DomainName] <String>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-DfsReplicationGroup** cmdlet modifies the configuration of existing replication groups.

A replication group is a set of servers, or members, that participate in the replication of one or more folders.
A replicated folder is kept synchronized among the members of a replication group.
This cmdlet cannot modify resource group bandwidth or schedules.

## EXAMPLES

### Example 1: Modify a replication group configuration
```
PS C:\> Set-DfsReplicationGroup -GroupName "RG01" -Description "Contoso Branch Office Data Collection for Backups"
GroupName              : RG01
DomainName             : corp.contoso.com
Identifier             : 1f06f8d4-a0ae-4221-99d2-0bd1bb27882b
UseScheduleInLocalTime : True
UseScheduleInUtc       : False
Description            : Contoso Branch Office Data Collection for Backups
```

This command modifies the description of a replication group named RG01.

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
Specifies a description for a replication group.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DomainName
Specifies a NetBIOS or fully qualified domain name (FQDN) for an Active Directory domain that contains the replication group.
If you do not specify this parameter, the cmdlet uses the current domain.

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
If you do not specify this parameter, the cmdlet queries for all participating replication groups.
You can specify multiple collections, separated by commas, as well as wildcard characters (*).

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: RG, RgName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.DistributedFileSystemReplication.DfsReplicationGroup

## OUTPUTS

### Microsoft.DistributedFileSystemReplication.DfsReplicationGroup

## NOTES

## RELATED LINKS

[Get-DfsReplicationGroup](./Get-DfsReplicationGroup.md)

[New-DfsReplicationGroup](./New-DfsReplicationGroup.md)

[Remove-DfsReplicationGroup](./Remove-DfsReplicationGroup.md)

