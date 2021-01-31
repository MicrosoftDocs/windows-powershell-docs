---
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
Module Name: WebAdministration
online version: 
schema: 2.0.0
title: Stop-Website
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 70B6FEA0-E95A-42FA-9699-7B665FF42FC8
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Stop-Website

## SYNOPSIS
Stops an IIS website.

## SYNTAX

```
Stop-Website [[-Name] <String>] [-Passthru] [<CommonParameters>]
```

## DESCRIPTION
The **Stop-Website** cmdlet stops the specified Internet Information Services (IIS) website.

## EXAMPLES

### Example 1: Stopping a web site
```
IIS:\>Stop-WebSite -Name "Default Web Site"
```

This command stops the site named Default Web Site.

## PARAMETERS

### -Name
Specifies the name of the website that this cmdlet stops.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Passthru
Passes an object that represents the website to the pipeline.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
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

[Start-WebAppPool](./Start-WebAppPool.md)

[Start-WebItem](./Start-WebItem.md)

[Stop-WebAppPool](./Stop-WebAppPool.md)

[Stop-WebItem](./Stop-WebItem.md)

[Get-Website](./Get-Website.md)

[New-Website](./New-Website.md)

[Remove-Website](./Remove-Website.md)

[Start-Website](./Start-Website.md)

