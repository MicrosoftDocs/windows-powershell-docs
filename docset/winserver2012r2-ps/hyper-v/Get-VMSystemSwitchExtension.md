---
external help file: Microsoft.HyperV.PowerShell.dll-Help.xml
Module Name: Hyper-V
online version: 
schema: 2.0.0
title: Get-VMSystemSwitchExtension
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: E8DA9E34-DD09-485E-9832-9B6D136BF1D5
---

# Get-VMSystemSwitchExtension

## SYNOPSIS
Gets the switch extensions installed on a virtual machine host.

## SYNTAX

```
Get-VMSystemSwitchExtension [-Name <String[]>] [-ComputerName <String[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-VMSystemSwitchExtension** cmdlet gets the switch extensions installed on a virtual machine host.
The returned switch extension does not contain embedded objects for features or an array of feature IDs.

## EXAMPLES

### Example 1
```
PS C:\>Get-VMSystemSwitchExtension
```

Gets all virtual switch extensions installed on the system.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts from which the switch extensions are to be retrieved.
NetBIOS names, IP addresses, and fully-qualified domain names are allowable.
The default is the local computer - use "localhost" or a dot (".") to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: .
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the switch extension to be retrieved.

```yaml
Type: String[]
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

### Microsoft.HyperV.PowerShell.SystemSwitchExtension

## NOTES

## RELATED LINKS

