---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-anbarr
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Mpio-help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/27/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-MSDSMGlobalDefaultLoadBalancePolicy
ms.reviewer:
ms.assetid: 38B5EFB4-24BF-4695-8E4A-62ABBDF09667
---

# Get-MSDSMGlobalDefaultLoadBalancePolicy

## SYNOPSIS
Gets the default load balance policy for MPIO devices.

## SYNTAX

```
Get-MSDSMGlobalDefaultLoadBalancePolicy [<CommonParameters>]
```

## DESCRIPTION
The **Get-MSDSMGlobalDefaultLoadBalancePolicy** cmdlet gets the default load balance policy for Microsoft Multipath I/O (MPIO) devices.
You can use the **Set-MSDSMGlobalDefaultLoadBalancePolicy** cmdlet to change the policy.
Microsoft Device Specific Module (MSDSM) applies this policy only to devices that it claims after you set the policy.

The cmdlet returns a string that contains one of these values: 

- None.
No currently configured default load balance policy.
- FOO.
Fail Over Only. 
- RR.
Round Robin.
- LQD.
Least Queue Depth.
- LB.
Least Blocks.

## EXAMPLES

### Example 1: Get load balance policy
```
PS C:\> Get-MSDSMGlobalDefaultLoadBalancePolicy 
RR
```

This command gets the global default load balance policy, in this case, RR for round robin.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### System.String

## NOTES

## RELATED LINKS

[Set-MSDSMGlobalDefaultLoadBalancePolicy](./Set-MSDSMGlobalDefaultLoadBalancePolicy.md)

