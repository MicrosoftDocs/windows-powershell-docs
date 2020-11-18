---
external help file: WssCmdlets.dll-Help.xml
online version: 
schema: 2.0.0
title: Set-WssRemoteWebAccessTitle
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 61B1BBAC-9B38-439F-AADF-63832296BFE7
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Set-WssRemoteWebAccessTitle

## SYNOPSIS
Modifies the title string of a Remote Web Access website.

## SYNTAX

```
Set-WssRemoteWebAccessTitle -Title <String> [<CommonParameters>]
```

## DESCRIPTION
The **Set-WssRemoteWebAccessTitle** cmdlet modifies the title string of a Remote Web Access website in sbs_sbs8_2.
The title string appears in the middle of the logon page.

## EXAMPLES

### Example 1: Modify the title for Remote Web Access
```
PS C:\> Set-WssRemoteWebAccessTitle -Title "Contoso Remote Web Access"
```

This command modifies the title for a Remote Access Web website.

## PARAMETERS

### -Title
Specifies a title string for the Remote Web Access website.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-WssRemoteWebAccessTitle](./Get-WssRemoteWebAccessTitle.md)

