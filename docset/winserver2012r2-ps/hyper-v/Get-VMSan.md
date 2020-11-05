---
external help file: Microsoft.HyperV.PowerShell.dll-Help.xml
Module Name: Hyper-V
online version: 
schema: 2.0.0
title: Get-VMSan
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
ms.assetid: 503032C8-E935-4E3E-A42E-0A845D541217
---

# Get-VMSan

## SYNOPSIS
Gets the available virtual machine storage area networks on a Hyper-V host or hosts.

## SYNTAX

```
Get-VMSan [[-Name] <String[]>] [-ComputerName <String[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-VMSan** cmdlet gets the available virtual storage area networks (SANs) on one or more Hyper-V hosts.

## EXAMPLES

### Example 1
```
PS C:\> Get-VMSan -Name ProductionSAN
```

Gets a virtual storage area network (SAN) named ProductionSAN.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts from which the available virtual machine storage area networks (SANs) are to be retrieved.
NetBIOS names, IP addresses, and fully-qualified domain names are allowable.
The default is the local computer - use "localhost" or a dot (".") to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: .
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the friendly name of a virtual storage area network (SAN) to be retrieved.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: SanName

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.HyperV.VMSan

## NOTES

## RELATED LINKS

