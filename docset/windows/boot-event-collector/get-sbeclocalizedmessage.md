---
author: brianlic-msft
description: 
external help file: BootEventCollector-help.xml
keywords: powershell, cmdlet
manager: alanth
ms.date: 2016-12-20
ms.prod: powershell
ms.technology: powershell
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-SbecLocalizedMessage
ms.assetid: 949374B5-4211-4638-8B23-DD1B7A34CDDA
---

# Get-SbecLocalizedMessage

## SYNOPSIS
Gets a localized message string.

## SYNTAX

```
Get-SbecLocalizedMessage [-Name] <String> [<CommonParameters>]
```

## DESCRIPTION
The **Get-SbecLocalizedMessage** cmdlet gets a localized message string by its name.

Because message strings for Setup and Boot Event Collector error message are localized, identifying errors returned by Setup and Boot Event Collector commands in the scripts requires that you can identify the meaning of the localized text.

$PsHome\Modules\BootEventCollector\$PsCulture\BootEventCollectorStrings.psd1 contains the localized strings and their names.
Specify the name of the localized message to get it.

If the name is not known, the cmdlet will throw an error.

## EXAMPLES

### 1:
```

```

## PARAMETERS

### -Name
Specifies the name of the localized message to get.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None.

## OUTPUTS

### string
This cmdlet gets the text of the localized message.

## NOTES

## RELATED LINKS

