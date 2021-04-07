---
author: Kateyanne
description: 
external help file: Microsoft.HyperV.PowerShell.dll-Help.xml
manager: jasgro
Module Name: Hyper-V
ms.author: v-kaunu
ms.date: 10/30/2017
ms.prod: powershell
ms.reviewer: brianlic
ms.topic: reference
online version: https://docs.microsoft.com/powershell/module/hyper-v/get-vmhostnumanodestatus?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-VMHostNumaNodeStatus
---

# Get-VMHostNumaNodeStatus

## SYNOPSIS
Gets the status of the virtual machines on the non-uniform memory access (NUMA) nodes of a virtual machine host or hosts.

## SYNTAX

```
Get-VMHostNumaNodeStatus [[-ComputerName] <String[]>] [-Id <Int32>] [<CommonParameters>]
```

## DESCRIPTION
Gets the status of the virtual machines on the non-uniform memory access (NUMA) nodes of a virtual machine host or hosts.
If the virtual machine host enables NUMA spanning, this cmdlet returns an error.

## EXAMPLES

### Example 1
```
PS C:\>Get-VMHostNumaNodeStatus
```

Gets the status of the virtual machines on the non-uniform memory access (NUMA) nodes of the local Hyper-V host.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts on which NUMA node status is to be retrieved.
NetBIOS names, IP addresses, and fully-qualified domain names are allowable.
The default is the local computer - use "localhost" or a dot (".") to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: .
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Id
Identifies a NUMA node for which virtual machine status is to be retrieved.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### VMNumaNodeStatus[]

## NOTES

## RELATED LINKS

