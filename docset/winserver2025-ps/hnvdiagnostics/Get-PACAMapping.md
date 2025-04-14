---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Get-PACAMapping.psm1-help.xml
Module Name: HNVDiagnostics
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hnvdiagnostics/get-pacamapping?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PACAMapping
---

# Get-PACAMapping

## SYNOPSIS
Gets virtual network mapping.

## SYNTAX

```
Get-PACAMapping [<CommonParameters>]
```

## DESCRIPTION
The **Get-PACAMapping** cmdlet gets the virtual network mapping for virtual machines hosted on a physical server.

This cmdlet displays a table with the following information:

- Customer Address (CA).
The IP address assigned to the virtual machine NIC on the tenant virtual machine that is connected to a virtual subnet.
- Virtual Subnet ID.
A unique value per virtual subnet that corresponds to the VxLAN Network Identifier (VNI) or the NVGRE Tenant Network Identifier (TNI) in the VxLAN and NVGRE headers, respectively.
- Provider Address (PA).
The IP address assigned to a hidden network adapter on the Hyper-V host.
This IP address is used as the encapsulating packets' Layer-3 IP header.
- MAC Address.
The CA MAC address assigned to the tenant virtual machine.

## EXAMPLES

### Example 1: Get virtual network mapping
```
PS C:\> Get-PACAMapping
CA IP Address CA MAC Address    Virtual Subnet ID PA IP Address
------------- --------------    ----------------- -------------
24.30.1.101   00-15-5D-3A-55-01              4098 10.10.182.69
24.30.3.182   00-15-5D-3A-57-02              4100 10.10.182.64
24.30.2.153   00-15-5D-3A-56-03              4099 10.10.182.64
192.168.0.11  00-1D-C8-B7-01-01              4096 10.10.182.64
192.168.0.10  00-1D-C8-B7-01-00              4096 10.10.182.66
24.30.2.152   00-15-5D-3A-56-02              4099 10.10.182.66
24.30.3.181   00-15-5D-3A-57-01              4100 10.10.182.65
24.30.3.183   00-15-5D-3A-57-03              4100 10.10.182.65
192.168.1.10  00-1D-C8-B7-01-02              4097 10.10.182.65
24.30.2.1     00-1D-D8-EE-1C-00              4099 10.10.182.68
24.30.2.151   00-15-5D-3A-56-01              4099 10.10.182.68
24.30.1.1     00-1D-D8-EE-1C-00              4098 10.10.182.68
24.30.1.102   00-15-5D-3A-55-02              4098 10.10.182.67
24.30.1.103   00-15-5D-3A-55-03              4098 10.10.182.6
```

This command gets the mapping of the virtual network.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

