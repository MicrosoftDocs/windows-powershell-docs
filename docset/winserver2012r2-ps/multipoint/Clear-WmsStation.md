---
external help file: WmsCmdlets.dll-Help.xml
Module Name: WmsCmdlets
online version: 
schema: 2.0.0
title: Clear-WmsStation
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/06/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: CF10CF86-649C-441A-BFD3-A8C56C690080
ms.reviewer:
ms.author: v-kaunu
---

# Clear-WmsStation

## SYNOPSIS
Clears station mapping information for all stations.

## SYNTAX

```
Clear-WmsStation [-TimeoutInSecond <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The Clear-WmsStation cmdlet clears station mapping information for all stations.

## EXAMPLES

### Example
```
PS C:\> Clear-WmsStation
No output.
```

All Windows MultiPoint Server stations will be in an unmapped state.
All station mapping information be lost, along with any specified station friendly name and station autologon information. 

Running Get-WmsStation now returns no station information.

### 1:
```
PS C:\>
```

## PARAMETERS

### -TimeoutInSecond
The timeout value in seconds before the operation is aborted.

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

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### None

## NOTES

## RELATED LINKS

