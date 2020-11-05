---
external help file: WssCmdlets.dll-Help.xml
online version: 
schema: 2.0.0
title: Set-WssRemoteWebAccessLogo
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 2BACCC6D-141D-4238-BEFF-B2C748076A3A
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Set-WssRemoteWebAccessLogo

## SYNOPSIS
Sets the path and filename of the logo image for the Remote Web Access website.

## SYNTAX

```
Set-WssRemoteWebAccessLogo -ImagePath <String> [<CommonParameters>]
```

## DESCRIPTION
The **Set-WssRemoteWebAccessLogo** cmdlet sets the path and filename of the logo for the Remote Web Access website in sbs_sbs8_2.
The logo image customizes the appearance of the Remote Web Access website.

## EXAMPLES

### Example 1: Set the name of the logo file
```
PS C:\> Set-WssRemoteWebAccessLogon -ImagePath "D:\Contoso-Logo.png"
```

This command sets the filename for the logo image displayed on the Remote Web Access website.

## PARAMETERS

### -ImagePath
Specifies the file path of the logo image.
To obtain the best results, use an image that is 32x32 pixels.

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

[Get-WssRemoteWebAccessLogo](./Get-WssRemoteWebAccessLogo.md)

