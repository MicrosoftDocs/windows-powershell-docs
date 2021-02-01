---
external help file: WmsCmdlets.dll-Help.xml
Module Name: WmsCmdlets
online version: 
schema: 2.0.0
title: Split-WmsStation
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/06/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 8943916B-321A-404E-B004-130EAD0FB89F
ms.reviewer:
ms.author: v-kaunu
---

# Split-WmsStation

## SYNOPSIS
Splits the specified station.

## SYNTAX

```
Split-WmsStation [-SplitVertical <String>] [-StationId <UInt32>] [-TimeoutInSecond <Int32>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The Split-WmsStation cmdlet splits the specified station into two stations.

## EXAMPLES

### Example
```
PS C:\> Split-WmsStation -StationId 1 -SplitVertical True
No output.
```

Station ID #1 will be split in to two stations.

### 1:
```
PS C:\>
```

## PARAMETERS

### -SplitVertical
Splits a station vertically.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StationId
The Windows MultiPoint Server station ID.

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
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs. The cmdlet is not run.

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

