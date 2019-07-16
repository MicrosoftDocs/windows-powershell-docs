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
title: Set-MSDSMGlobalDefaultLoadBalancePolicy
ms.reviewer:
ms.assetid: A23ADBC9-05DB-41B0-92C9-96E682E81C58
---

# Set-MSDSMGlobalDefaultLoadBalancePolicy

## SYNOPSIS
Sets the default load balance policy for MPIO devices.

## SYNTAX

```
Set-MSDSMGlobalDefaultLoadBalancePolicy [-Policy] <String> [<CommonParameters>]
```

## DESCRIPTION
The **Set-MSDSMGlobalDefaultLoadBalancePolicy** cmdlet sets the default load balance policy for Microsoft Multipath I/O (MPIO) devices.
Microsoft Device Specific Module (MSDSM) applies this policy only to devices that it claims after you set the policy.

Use the **Get-MSDSMGlobalDefaultLoadBalancePolicy** cmdlet to see the current default policy.

## EXAMPLES

### Example 1: Set round robin as default policy
```
PS C:\> Set-MSDSMGlobalLoadBalancePolicy -Policy RR
```

This command sets the default load balance policy to round robin.

### Example 2: Clear default policy
```
PS C:\> Set-MSDSMGlobalLoadBalancePolicy -Policy None
```

This command clears any current configured default load balance policy.

## PARAMETERS

### -Policy
Specifies a default value for load balance policy.
The acceptable values for this parameter are:

- None.
Clears any currently configured default load balance policy.
- FOO.
Fail Over Only. 
- RR.
Round Robin.
- LQD.
Least Queue Depth.
- LB.
Least Blocks.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 
Accepted values: None, FOO, RR, LQD, LB

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-MSDSMGlobalDefaultLoadBalancePolicy](./Get-MSDSMGlobalDefaultLoadBalancePolicy.md)

