---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Get-ProviderAddress.psm1-help.xml
Module Name: HNVDiagnostics
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hnvdiagnostics/get-provideraddress?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ProviderAddress
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

### None

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

