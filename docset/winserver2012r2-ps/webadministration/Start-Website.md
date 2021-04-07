---
author: Kateyanne
description: 
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
manager: jasgro
Module Name: WebAdministration
ms.author: v-kaunu
ms.date: 10/30/2017
ms.prod: powershell
ms.reviewer: brianlic
ms.topic: reference
online version: https://docs.microsoft.com/powershell/module/webadministration/start-website?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Start-Website
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

### Example 1: Starting a web site
```
IIS:\>Start-WebSite -Name "Default Web Site"
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-Website](./Get-Website.md)

[New-Website](./New-Website.md)

[Remove-Website](./Remove-Website.md)

[Stop-Website](./Stop-Website.md)

