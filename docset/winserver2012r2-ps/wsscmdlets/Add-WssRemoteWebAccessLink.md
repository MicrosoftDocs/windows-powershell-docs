---
external help file: WssCmdlets.dll-Help.xml
online version: 
schema: 2.0.0
title: Add-WssRemoteWebAccessLink
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 8F64B520-98EE-4D08-96B6-FFE281F3DB74
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Add-WssRemoteWebAccessLink

## SYNOPSIS
Adds a link to the home page of a Remote Web Access website.

## SYNTAX

```
Add-WssRemoteWebAccessLink -Text <String> -Url <Uri> [<CommonParameters>]
```

## DESCRIPTION
The **Add-WssRemoteWebAccessLink** cmdlet adds a link to the home page of a Remote Web Access website.

To remove a link from the home page of a Remote Web Access website, use the **Remove-WssRemoteWebAccessLink** cmdlet.

## EXAMPLES

### Example 1: Add a link to a home page
```
PS C:\> Add-WssRemoteWebAccessLink -Text "Link1" -Url "http://Contoso.com/About-Contoso-Page.html"
```

This command adds a link to the home page for a Remote Web Access website.

## PARAMETERS

### -Text
Specifies a text string for a link that displays on the home page.

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

### -Url
Specifies a web address for the link, as an absolute URI.

```yaml
Type: Uri
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

[Get-WssRemoteWebAccessLink](./Get-WssRemoteWebAccessLink.md)

[Remove-WssRemoteWebAccessLink](./Remove-WssRemoteWebAccessLink.md)

