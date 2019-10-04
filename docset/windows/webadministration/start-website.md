---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-anbarr
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/27/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Start-Website
ms.reviewer:
ms.assetid: C2665D45-523E-401E-858D-85FD0AA6A8ED
---

# Start-Website

## SYNOPSIS
Starts an IIS website.

## SYNTAX

```
Start-Website [[-Name] <String>] [-Passthru] [<CommonParameters>]
```

## DESCRIPTION
The **Start-Website** cmdlet starts an existing site on the Internet Information Services (IIS) server.

## EXAMPLES

### Example 1: Start a website
```
IIS:\> Start-WebSite -Name "Default Web Site"
```

This command starts the site named Default Web Site.

## PARAMETERS

### -Name
Specifies the name of the website that this cmdlet starts.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-Website](./Get-Website.md)

[New-Website](./New-Website.md)

[Remove-Website](./Remove-Website.md)

[Stop-Website](./Stop-Website.md)

