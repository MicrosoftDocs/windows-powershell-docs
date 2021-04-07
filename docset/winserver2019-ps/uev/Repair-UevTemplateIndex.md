---
author: Kateyanne
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Uev.Commands.dll-Help.xml
manager: jasgro
Module Name: UEV
ms.author: v-kaunu
ms.date: 12/20/2016
ms.mktglfcycl: manage
ms.prod: w10
ms.reviewer: 
ms.sitesec: library
ms.technology: 
ms.topic: reference
online version: https://docs.microsoft.com/powershell/module/uev/repair-uevtemplateindex?view=windowsserver2019-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Repair-UevTemplateIndex
---

# Repair-UevTemplateIndex

## SYNOPSIS
Repairs a corrupted UE-V template index.

## SYNTAX

```
Repair-UevTemplateIndex [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Repair-UevTemplateIndex** cmdlet repairs the index for the Microsoft User Experience Virtualization (UE-V) settings location templates.
A corrupted template prevents you from enumerating the UE-V templates, and can prevent UE-V from synchronizing settings for any application on the computer.
You must have administrator privileges to run this cmdlet.

## EXAMPLES

### Example 1: Repair the template index
```
PS C:\> Repair-UevTemplateIndex
```

This command repairs the corrupted template index.

## PARAMETERS

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

