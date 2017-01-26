---
author: brianlic-msft
description: 
external help file: Get-CustomerRoute-help.xml
keywords: powershell, cmdlet
manager: alanth
ms.date: 2016-12-20
ms.prod: powershell
ms.technology: powershell
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-CustomerRoute
ms.assetid: 2A3B00FC-EF81-4DF7-B1DA-6852D94D5EBA
---

# Get-CustomerRoute

## SYNOPSIS
Gets CA routes.

## SYNTAX

```
Get-CustomerRoute [<CommonParameters>]
```

## DESCRIPTION
The **Get-CustomerRoute** cmdlet gets Customer Address (CA) routing information organized by Routing Domain ID (RDID).
The information includes: 

- Virtual Subnet ID (VSID).
This value is unique per virtual subnet, and corresponds to the VxLAN Network Identifier (VNI) or the NVGRE Tenant Network Identifier (TNI) in the VxLAN and NVGRE headers, respectively. 
- CA IP Prefix.
IP prefix for the virtual subnet. 
- CA IP Prefix Length.
Length (or subnet mask) of the CA IP Prefix. 
- CA IP Next Hop.
The next hop required to reach the specified CA IP Prefix, usually the default gateway assigned to the HNV distributed router. 
- Routing Doman ID.

## EXAMPLES

### 1:
```
PS C:\>
```

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

