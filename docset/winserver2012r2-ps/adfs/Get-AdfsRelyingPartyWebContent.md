---
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: ADFS
online version: 
schema: 2.0.0
title: Get-AdfsRelyingPartyWebContent
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 91C9088C-17A7-4D18-8DC7-9B2918B14E82
---

# Get-AdfsRelyingPartyWebContent

## SYNOPSIS
Gets web content objects for relying parties.

## SYNTAX

```
Get-AdfsRelyingPartyWebContent [-Locale <CultureInfo>] [-Name <String[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AdfsRelyingPartyWebContent** cmdlet gets web content objects for relying parties.
Specify a relying party by name.
If you do not specify a name, the cmdlet gets all relying party web content objects.
If you do not specify a locale, the cmdlet gets web content for all locales.

## EXAMPLES

### Example 1: Get all web content objects
```
PS C:\> Get-AdfsRelyingPartyWebContent
```

This command gets web content objects for all relying parties and locales.

### Example 2: Get web content objects for a specified relying party
```
PS C:\> Get-AdfsRelyingPartyWebContent -Name "RelyingParty01"
```

This command gets web content objects for the relying party named RelyingParty01 for all locales.

### Example 3: Get the web content object for a specified relying party and locale
```
PS C:\> Get-AdfsRelyingPartyWebContent -Locale en-us -Name "RelyingParty01"
```

This command gets web content objects for the relying party named RelyingParty01 for the specified locale.

## PARAMETERS

### -Locale
Specifies a locale.
The cmdlet gets relying party web content for the locale that you specify.

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
Specifies a name.
The cmdlet gets web content for the relying party that you specify by name.

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

### Microsoft.IdentityServer.Management.Resources.AdfsRelyingPartyWebContent;Microsoft.IdentityServer.Management.Resources.AdfsRelyingPartyWebContent[]
This cmdlet generates a **System.IdentityServer.Management.Resources.AdfsRelyingPartyWebContent** object that represents web content of a relying party, or an array of such objects.
The object includes the following properties: 

Locale: **System.Globalization.CultureInfo**
Name: **System.String**
ErrorPageGenericErrorMessage: **System.String**
ErrorPageAuthorizationErrorMessage: **System.String**
ErrorPageDeviceAuthenticationErrorMessage: **System.String**

## NOTES

## RELATED LINKS

[Remove-AdfsRelyingPartyWebContent](./Remove-AdfsRelyingPartyWebContent.md)

[Set-AdfsRelyingPartyWebContent](./Set-AdfsRelyingPartyWebContent.md)

