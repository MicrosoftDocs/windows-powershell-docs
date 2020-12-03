---
ms.technology: 
ms.mktglfcycl: manage
ms.author: v-kaunu
ms.prod: w10
ms.sitesec: library
author: Kateyanne
description: Use this topic to help manage MDOP technologies with Windows PowerShell.
external help file: Microsoft.Uev.Commands.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro 
ms.assetid: 0D960A1F-DC61-4326-9AE9-B28E1177A840
ms.date: 12/05/2016
ms.devlang: powershell
ms.topic: reference
online version: 
schema: 2.0.0
title: Repair-UevTemplateIndex
ms.reviewer:
---

# Repair-UevTemplateIndex

## SYNOPSIS
Repairs a corrupted uev_tla template index.

## SYNTAX

```
Repair-UevTemplateIndex [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Repair-UevTemplateIndex** cmdlet repairs the index for the uev_1 settings location templates.
A corrupted template prevents you from enumerating the uev_tla templates, and can prevent uev_tla from synchronizing settings for any application on the computer.
You must have administrator privileges to run this cmdlet.

## EXAMPLES

### Example 1: Repair the template index
```
PS C:\> Repair-UevTemplateIndex
```

This command repairs the corrupted template index.

## PARAMETERS

### -Confirm
Prompts you for confirmation before running the cmdlet.Prompts you for confirmation before running the cmdlet.

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
The cmdlet is not run.Shows what would happen if the cmdlet runs.
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

