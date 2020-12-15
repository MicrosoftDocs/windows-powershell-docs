---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-kaunu
author: Kateyanne
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Get-ProviderAddress-help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: 
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-ProviderAddress
ms.reviewer:
ms.assetid: 86BBA0AA-2D7A-4E05-A141-86B3E403DA73
---

# Get-ProviderAddress

## SYNOPSIS
Gets the provider address for a server.

## SYNTAX

```
Get-ProviderAddress [<CommonParameters>]
```

## DESCRIPTION
The **Get-ProviderAddress** cmdlet gets the provider address (PA) for a physical server.
This cmdlet gets the following information: 

- Provider Address (PA).
The IP address assigned to a hidden network adapter in a non-default network compartment. 
- Subnet mask.
The IP prefix length, or mask, of the PA IP address. 
- MAC Address.
The media access control address. 
- Default gateway.
The default gateway (next-hop) for the specified PA IP address.
This typically corresponds to the IP address assigned to the top-of-rack (ToR) switch.

## EXAMPLES

### Example 1: Get the provider address
```
PS C:\> Get-ProviderAddress
ProviderAddress : 10.10.182.68
MAC Address     : 00-1D-D8-EE-1C-07
Subnet Mask     : 255.255.255.128
Default Gateway : 10.10.182.1
VLAN            : VLAN11
ProviderAddress : 10.10.182.69
MAC Address     : 00-1D-D8-EE-1C-09
Subnet Mask     : 255.255.255.128
Default Gateway : 10.10.182.1
VLAN            : VLAN11
```

This command gets the provider address.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

