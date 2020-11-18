---
external help file: Microsoft.HyperV.PowerShell.dll-Help.xml
Module Name: Hyper-V
online version: 
schema: 2.0.0
title: Get-VMHost
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
ms.assetid: 6D098940-C925-4776-96FF-95EDD347C7F5
---

# Get-VMHost

## SYNOPSIS
Gets a Hyper-V host.

## SYNTAX

```
Get-VMHost [[-ComputerName] <String[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-VMHost** cmdlet gets a Hyper-V host.

## EXAMPLES

### Example 1
```
PS C:\>Get-VMHost
```

Gets the local Hyper-V host.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts to be retrieved.
NetBIOS names, IP addresses, and fully-qualified domain names are allowable.
The default is the local computer - use "localhost" or a dot (".") to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: .
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.HyperV.PowerShell.Host

## NOTES

## RELATED LINKS

