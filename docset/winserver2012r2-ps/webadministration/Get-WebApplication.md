---
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
Module Name: WebAdministration
online version: 
schema: 2.0.0
title: Get-WebApplication
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 76C3A941-6AAB-4F53-ACE4-F7FDA7244E7D
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Get-WebApplication

## SYNOPSIS
Gets the web applications associated with a specific site or with a specified name.

## SYNTAX

```
Get-WebApplication [-Site <String>] [[-Name] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-WebApplication** cmdlet gets the web applications associated with a specific site or with a specified name.

## EXAMPLES

### Example 1: Gets the web applications associated with the default web site
```powershell
IIS:\>Get-WebApplication -Site "Default Web Site"

Name             Application pool   Protocols    Physical Path
----             ----------------   ---------    -------------
Test             DefaultAppPool     http         C:\inetpub\wwwroot\
```

This command gets the web applications associated with the default website.

## PARAMETERS

### -Name
Specifies the name of the web application for which information is returned.

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

### -Site
Specifies the name of the site for which this cmdlet returns application information.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[ConvertTo-WebApplication](./ConvertTo-WebApplication.md)

[New-WebApplication](./New-WebApplication.md)

[Remove-WebApplication](./Remove-WebApplication.md)

[Microsoft.Web.Administration.ConfigurationElement#Application](https://docs.microsoft.com/dotnet/api/microsoft.web.administration.application?view=iis-dotnet)
