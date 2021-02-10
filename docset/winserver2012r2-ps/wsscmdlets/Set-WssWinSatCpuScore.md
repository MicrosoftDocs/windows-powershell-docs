---
external help file: WssCmdlets.dll-Help.xml
online version: 
schema: 2.0.0
title: Set-WssWinSatCpuScore
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 7A13CE3C-D9E3-4E2F-B09D-815634A55511
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Set-WssWinSatCpuScore

## SYNOPSIS
Modifies the Windows Experience Index processor subscore.

## SYNTAX

```
Set-WssWinSatCpuScore [-WinSatCpuScore] <Double> [<CommonParameters>]
```

## DESCRIPTION
The **Set-WssWinSatCpuScore** cmdlet modifies the Windows Experience Index (WinSAT) processor subscore.

## EXAMPLES

### Example 1: Modify the WinSAT score
```
PS C:\> Set-WssWinSatCpuScore -WinSatCpuScore 1
```

This command modifies the WinSAT score.

## PARAMETERS

### -WinSatCpuScore
Specifies a WinSAT CPU score.

```yaml
Type: Double
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-WssWinSatCpuScore](./Get-WssWinSatCpuScore.md)

