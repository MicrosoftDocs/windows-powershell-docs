---
external help file: WmsCmdlets.dll-Help.xml
Module Name: WmsCmdlets
online version: 
schema: 2.0.0
title: Register-WmsEvent
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/06/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: F1ED493B-FDD7-4F95-9820-36550B5AEB99
ms.reviewer:
ms.author: v-kaunu
---

# Register-WmsEvent

## SYNOPSIS
Registers for notifications from the MultiPoint Server Core Service.

## SYNTAX

```
Register-WmsEvent [-TimeoutInSecond <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The Register-WmsEvent cmdlet registers for notifications from the MultiPoint Server Core Service.

## EXAMPLES

### Example
```
PS C:\> Register-WmsEvent
No output.
```

Registers to be notified on events from Windows MultiPoint Server Core Service.

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
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Describes what would happen if you executed the command without actually executing the command.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
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

