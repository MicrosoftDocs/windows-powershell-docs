---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-kaunu
author: Kateyanne
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/27/2016
ms.prod: w10
ms.technology: 
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-WebApplication
ms.reviewer:
ms.assetid: 76C3A941-6AAB-4F53-ACE4-F7FDA7244E7D
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

### Example 1: Get the web applications associated with the default website
```powershell
IIS:\> Get-WebApplication -Site "Default Web Site"

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