---
external help file: WmsCmdlets.dll-Help.xml
Module Name: WmsCmdlets
online version: 
schema: 2.0.0
title: Hide-WmsIdentifier
description: 
keywords: powershell, cmdlet
author: andreabarr
manager: jasgro
ms.date: 2017-12-06
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 26F90975-4C32-4077-A88F-7754CEF8AC82
ms.reviewer:
ms.author: v-anbarr
---

# Hide-WmsIdentifier

## SYNOPSIS
Hides identification window.

## SYNTAX

```
Hide-WmsIdentifier [-SessionId <UInt32>] [-StationId <UInt32>] [-TimeoutInSecond <Int32>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Hides identification window for the specified station or session.

## EXAMPLES

### Example
```
PS C:\>Hide-WmsIdentifier -SessionID 2
```

### 1:
```
PS C:\>
```

## PARAMETERS

### -SessionId
Session ID to identify.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -StationId
Station ID to identify.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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

###  
You cannot pipes to object to Hide-WmsIdentifier

## OUTPUTS

### None

## NOTES

## RELATED LINKS

