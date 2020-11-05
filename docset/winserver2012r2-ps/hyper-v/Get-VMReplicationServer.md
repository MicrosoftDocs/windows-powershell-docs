---
external help file: Microsoft.HyperV.PowerShell.dll-Help.xml
Module Name: Hyper-V
online version: 
schema: 2.0.0
title: Get-VMReplicationServer
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
ms.assetid: 93652B26-419B-4FC6-81C6-0AC9C35460EF
---

# Get-VMReplicationServer

## SYNOPSIS
Gets the replication and authentication settings of a Replica server.

## SYNTAX

```
Get-VMReplicationServer [[-ComputerName] <String[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-VMReplicationServer** cmdlet gets the replication and authentication settings of a Replica server.

## EXAMPLES

### Example 1
```
PS C:\> Get-VMReplicationServer
```

This example gets the replication configuration of the local Replica server.

### Example 2
```
PS C:\> Get-VMReplicationServer server01.domain01.contoso.com
```

This example gets the replication configuration of a server named server01.domain01.contoso.com.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts for which to retrieve replication and authentication settings.
NetBIOS names, IP addresses, and fully-qualified domain names are allowable.
The default is the local computer - use "localhost" or a dot (".") to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: .
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### VMReplicationServer

## NOTES

## RELATED LINKS

