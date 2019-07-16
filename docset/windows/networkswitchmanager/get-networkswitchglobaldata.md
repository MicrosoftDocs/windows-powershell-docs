---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-anbarr
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: NetworkSwitchGlobalSettingData-help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-NetworkSwitchGlobalData
ms.reviewer:
ms.assetid: EC6B335F-5E2E-463F-AC76-C2A17FF4F0E7
---

# Get-NetworkSwitchGlobalData

## SYNOPSIS
Gets global data of a network switch.

## SYNTAX

```
Get-NetworkSwitchGlobalData [-CimSession] <CimSession> [<CommonParameters>]
```

## DESCRIPTION
The **Get-NetworkSwitchGlobalData** cmdlet gets global data of a network switch.

## EXAMPLES

### Example 1: Get global data
```
PS C:\>$Session = New-CimSession -ComputerName "NetworkSwitch08"
PS C:\> Get-NetworkSwitchGlobalData -CimSession $Session
```

The first command creates a **CimSession** for a network switch, and then stores it in the **$Session** variable.
For more information about **CimSession** objects, type `Get-Help New-CimSession`.

The second command gets global data for the network switch NetworkSwitch08 by using the **$Session** object.

## PARAMETERS

### -CimSession
Specifies the **CimSession** that this cmdlet uses to connect to the network switch.
For more information about **CimSession** objects, type `Get-Help New-CimSession`.

```yaml
Type: CimSession
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### CimInstance
This cmdlet returns the **globalData** of the network switch as **CimInstance** object.

## NOTES

## RELATED LINKS

