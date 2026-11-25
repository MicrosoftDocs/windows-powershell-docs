---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Get-CustomerRoute.psm1-help.xml
Module Name: HNVDiagnostics
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hnvdiagnostics/get-customerroute?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-CustomerRoute
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
- Routing Domain ID.

## EXAMPLES


## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

