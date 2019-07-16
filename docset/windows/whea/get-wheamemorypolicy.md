---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-anbarr
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Windows.Whea.WheaMemoryPolicy.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-WheaMemoryPolicy
ms.reviewer:
ms.assetid: A9175E75-42E5-4E39-9DD5-8C37F7761214
---

# Get-WheaMemoryPolicy

## SYNOPSIS
Gets the WHEA memory policies for a computer.

## SYNTAX

```
Get-WheaMemoryPolicy [-ComputerName <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-WheaMemoryPolicy** cmdlet gets the Windows Hardware Error Architecture (WHEA) memory policies in effect on a local or remote computer.

## EXAMPLES

### Example 1: Get the WHEA memory policy settings from the local computer
```
PS C:\> Get-WHEAMemoryPolicy
DisableOffline : False
DisablePFA : False
PersistMemoryOffline : True
PFAPageCount : 64
PFAErrorThreshold : 16
PFATimeOut : 86400
```

This command gets WHEA memory policy values from the local computer as a **WheaMemoryPolicy** object.

## PARAMETERS

### -ComputerName
Specifies the name of the remote computer from which to retrieve policy information.
If you do not specify a computer name, the command returns the policy of the local computer.
The alias for *ComputerName* is cn.

```yaml
Type: String
Parameter Sets: (All)
Aliases: CN

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### WheaMemoryPolicy

## NOTES

## RELATED LINKS

[Set-WheaMemoryPolicy](./Set-WheaMemoryPolicy.md)

