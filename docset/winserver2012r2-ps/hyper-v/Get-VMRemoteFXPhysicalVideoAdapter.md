---
external help file: Microsoft.HyperV.PowerShell.dll-Help.xml
Module Name: Hyper-V
online version: 
schema: 2.0.0
title: Get-VMRemoteFXPhysicalVideoAdapter
ms.author: v-anbarr
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: andreabarr
manager: jasgro
ms.date: 2017-10-30
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: AC3EC4E0-60E7-43FE-8A6A-72071FB45433
---

# Get-VMRemoteFXPhysicalVideoAdapter

## SYNOPSIS
Gets the RemoteFX physical graphics adapters on one or more Hyper-V hosts.

## SYNTAX

```
Get-VMRemoteFXPhysicalVideoAdapter [-ComputerName <String[]>] [[-Name] <String[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-VMRemoteFXPhysicalVideoAdapter** cmdlet gets the RemoteFX physical graphics adapters on one or more Hyper-V hosts.

## EXAMPLES

### Example 1
```
PS C:\>Get-VMRemoteFXPhysicalVideoAdapter
```

Gets all RemoteFX physical video adapters on the Hyper-V host.

### Example 2
```
PS C:\>Get-VMRemoteFXPhysicalVideoAdapter -Name *Nvidia*
```

Gets all RemoteFX physical video adapters on the Hyper-V host which include the sequence Nvidia in their name.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts from which the RemoteFX physical graphics adapters are to be retrieved.
NetBIOS names, IP addresses, and fully-qualified domain names are allowable.
The default is the local computer - use "localhost" or a dot (".") to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: .
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Name
Specifies the names of one or more RemoteFX physical graphics adapters to be retrieved.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.HyperV.PowerShell.VMRemoteFXPhysicalVideoAdapter[]

## NOTES

## RELATED LINKS

