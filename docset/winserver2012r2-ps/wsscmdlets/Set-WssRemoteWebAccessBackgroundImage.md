---
external help file: WssCmdlets.dll-Help.xml
online version: 
schema: 2.0.0
title: Set-WssRemoteWebAccessBackgroundImage
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: BB8EA206-C564-4FC0-A445-518171FD0487
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Set-WssRemoteWebAccessBackgroundImage

## SYNOPSIS
Sets the background image for a Remote Web Access website.

## SYNTAX

```
Set-WssRemoteWebAccessBackgroundImage -ImagePath <String> [<CommonParameters>]
```

## DESCRIPTION
The **Set-WssRemoteWebAccessBackgroundImage** cmdlet sets a background image on the logon page of a Remote Web Access website.

## EXAMPLES

### Example 1: Set the background image
```
PS C:\> Set-WssRemoteWebAccessBackgroundImage -ImagePath "D:\Contoso-image.png"
```

This command sets the background image of the logon page.

## PARAMETERS

### -ImagePath
Specifies the path to an image file.
Use any of the following image types: 
- Bitmap (*.bmp, *.dib, *.rle) 
- GIF (*.gif) 
- PNG (*.png) 
- JPG (*.jpg)

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

[Get-WssRemoteWebAccessBackgroundImage](./Get-WssRemoteWebAccessBackgroundImage.md)

