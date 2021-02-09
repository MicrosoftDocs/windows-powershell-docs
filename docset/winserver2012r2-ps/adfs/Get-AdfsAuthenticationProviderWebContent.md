---
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: ADFS
online version: 
schema: 2.0.0
title: Get-AdfsAuthenticationProviderWebContent
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 9FDAEEBA-549F-40C4-82E1-2135CADFF187
---

# Get-AdfsAuthenticationProviderWebContent

## SYNOPSIS
Retrieves web content objects for authentication providers.

## SYNTAX

```
Get-AdfsAuthenticationProviderWebContent [-Locale <CultureInfo>] [-Name <String[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AdfsAuthenticationProviderWebContent** cmdlet retrieves web content objects for all authentication providers, or a specified authentication provider in a locale.
Specify an authentication provider by its name.
If you do not supply an authentication provider name, the cmdlet retrieves all authentication provider web content objects.
If you do not specify the locale, the cmdlet retrieves web content for all locales.
The cmdlet does not return any information if you do not use the Set-AdfsAuthenticationProviderWebContent cmdlet to customize the authentication provider web content.

## EXAMPLES

### 1:
```

```

## PARAMETERS

### -Locale
Specifies a locale.
The cmdlet gets the provider web content associated for the locale that you specify.

```yaml
Type: CultureInfo
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies a array of names.
The cmdlet gets the provider web content associated for the names that you specify.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Remove-AdfsAuthenticationProviderWebContent](./Remove-AdfsAuthenticationProviderWebContent.md)

[Set-AdfsAuthenticationProviderWebContent](./Set-AdfsAuthenticationProviderWebContent.md)

