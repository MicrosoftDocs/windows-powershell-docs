---
external help file: WmsCmdlets.dll-Help.xml
Module Name: WmsCmdlets
online version: 
schema: 2.0.0
title: Reset-WmsSystem
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/06/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 970a4b60-76fa-43f7-bb39-e7f27b2d8d69
ms.reviewer:
ms.author: v-kaunu
---

# Reset-WmsSystem

## SYNOPSIS
Shuts down the computer that is running Windows MultiPoint Server.

## SYNTAX

```
Reset-WmsSystem [-TimeoutInSecond <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The Stop-WmsSystem cmdlet shuts down the computer that is running Windows MultiPoint Server by using a Windows Management Instrumentation (WMI) call.

## EXAMPLES

### Example
```
PS C:\> Stop-WmsSystem
No output.
```

The system will be shut down.

### 1:
```
PS C:\>
```

## PARAMETERS

### -TimeoutInSecond
Specifies a Remote Desktop Session (RDS) using SessionID.

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

